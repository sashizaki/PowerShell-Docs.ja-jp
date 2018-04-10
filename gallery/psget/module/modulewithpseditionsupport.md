---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: modulewithpseditionsupport
ms.openlocfilehash: cc4ab8d41d4c6aace72cbeeabcf510fab6d3a999
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="a937d-103">互換性のある PowerShell エディションが含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="a937d-103">Modules with compatible PowerShell Editions</span></span>
<span data-ttu-id="a937d-104">バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="a937d-105">**デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a937d-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="a937d-106">**コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a937d-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

## <a name="the-running-edition-of-powershell-is-shown-in-the-psedition-property-of-psversiontable"></a><span data-ttu-id="a937d-107">PowerShell の実行中のエディションは、$PSVersionTable の PSEdition プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a937d-107">The running edition of PowerShell is shown in the PSEdition property of $PSVersionTable.</span></span>
```powershell
$PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.14300.1000
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.14300.1000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

## <a name="module-authors-can-declare-their-modules-to-be-compatible-with-one-or-more-powershell-editions-using-the-compatiblepseditions-module-manifest-key-this-key-is-only-supported-on-powershell-51-or-later"></a><span data-ttu-id="a937d-108">モジュールの作成者は、CompatiblePSEditions モジュール マニフェスト キーを使用して、モジュールが 1 つ以上の PowerShell エディションと互換性があることを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-108">Module authors can declare their modules to be compatible with one or more PowerShell editions using the CompatiblePSEditions module manifest key.</span></span> <span data-ttu-id="a937d-109">このキーは、PowerShell 5.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a937d-109">This key is only supported on PowerShell 5.1 or later.</span></span>
<span data-ttu-id="a937d-110">*注*: CompatiblePSEditions キーを使用してモジュール マニフェストを指定した後は、古いバージョンの PowerShell でもインポートできます。</span><span class="sxs-lookup"><span data-stu-id="a937d-110">*NOTE* Once a module manifest is specified with the CompatiblePSEditions key, it can not be imported on lower versions of PowerShell.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
Desktop
Core

$ModuleInfo | Get-Member CompatiblePSEditions

   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}

```
<span data-ttu-id="a937d-111">使用可能なモジュールの一覧を取得するときには、PowerShell のエディションを条件としてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-111">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>
```powershell
Get-Module -ListAvailable -PSEdition Desktop

    Directory: C:\Program Files\WindowsPowerShell\Modules


ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions

Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
Desktop
Core

```

## <a name="module-authors-can-publish-a-single-module-targeting-to-either-or-both-powershell-editions-desktop-and-core"></a><span data-ttu-id="a937d-112">モジュールの作成者が、PowerShell エディションのどちらかまたは両方を対象とする 1 つのモジュールを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="a937d-112">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core)</span></span>

<span data-ttu-id="a937d-113">1 つのモジュールが、デスクトップとコアの両方のエディションで動作します。そのモジュール内で、作成者は、$PSEdition 変数を使用して、RootModule またはモジュール マニフェストで必要なロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a937d-113">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using $PSEdition variable.</span></span>
<span data-ttu-id="a937d-114">モジュールでは、CoreCLR と FullCLR の両方を対象とするコンパイル済み DLL の 2 つのセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-114">Modules can have two sets of compiled DLLs targeting both CoreCLR and FullCLR.</span></span>
<span data-ttu-id="a937d-115">次に、適切な dll を読み込むためのロジックを含むモジュールをパッケージ化するためのいくつかのオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="a937d-115">Here are the couple of options to package your module with logic for loading proper dlls.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="a937d-116">オプション 1: PowerShell の複数のバージョンおよび複数のエディションを対象としてパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="a937d-116">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

#### <a name="module-folder-contents"></a><span data-ttu-id="a937d-117">モジュール フォルダーの内容</span><span class="sxs-lookup"><span data-stu-id="a937d-117">Module folder contents</span></span>
- <span data-ttu-id="a937d-118">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="a937d-118">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="a937d-119">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="a937d-119">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="a937d-120">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="a937d-120">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="a937d-121">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="a937d-121">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="a937d-122">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="a937d-122">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="a937d-123">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="a937d-123">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="a937d-124">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="a937d-124">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="a937d-125">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="a937d-125">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="a937d-126">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="a937d-126">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="a937d-127">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="a937d-127">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="a937d-128">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="a937d-128">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="a937d-129">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="a937d-129">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="a937d-130">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="a937d-130">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="a937d-131">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="a937d-131">Settings\DSC.psd1</span></span>
- <span data-ttu-id="a937d-132">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="a937d-132">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="a937d-133">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="a937d-133">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="a937d-134">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="a937d-134">Settings\ScriptSecurity.psd1</span></span>

#### <a name="contents-of-psscriptanalyzerpsd1-file"></a><span data-ttu-id="a937d-135">PSScriptAnalyzer.psd1 ファイルの内容</span><span class="sxs-lookup"><span data-stu-id="a937d-135">Contents of PSScriptAnalyzer.psd1 file</span></span>

```powershell
@{

# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

#### <a name="contents-of-psscriptanalyzerpsm1-file"></a><span data-ttu-id="a937d-136">PSScriptAnalyzer.psm1 ファイルの内容</span><span class="sxs-lookup"><span data-stu-id="a937d-136">Contents of PSScriptAnalyzer.psm1 file</span></span>
<span data-ttu-id="a937d-137">以下のロジックは、現在のエディションまたはバージョンに応じて必要なアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a937d-137">Below logic loads the required assemblies depending on the current edition or version.</span></span>

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0') {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
}

```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls-and-nestedrequired-modules"></a><span data-ttu-id="a937d-138">オプション 2: PSD1 ファイルで $PSEdition 変数を使用して適切な DLL と入れ子になった/必要なモジュールを読み込む</span><span class="sxs-lookup"><span data-stu-id="a937d-138">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs and Nested/Required modules</span></span>

<span data-ttu-id="a937d-139">PS 5.1 以降では、$PSEdition グローバル変数をモジュール マニフェスト ファイル内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-139">In PS 5.1 or newer, $PSEdition global variable is allowed in the module manifest file.</span></span>
<span data-ttu-id="a937d-140">この変数を使用すると、モジュールの作成者が、モジュール マニフェスト ファイル内で条件値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-140">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="a937d-141">$PSEdition 変数は、制限された言語モードまたはデータ セクション内で参照できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-141">$PSEdition variable can be referenced in restricted language mode or a Data section.</span></span>

<span data-ttu-id="a937d-142">*注*: CompatiblePSEditions キーまたは $PSEdition 変数を使用してモジュール マニフェストを指定した後は、古いバージョンの PowerShell でもインポートできます。</span><span class="sxs-lookup"><span data-stu-id="a937d-142">*NOTE* Once a module manifest is specified with the CompatiblePSEditions key or uses $PSEdition variable, it can not be imported on lower versions of PowerShell.</span></span>


#### <a name="sample-module-manifest-file-with-compatiblepseditions-key"></a><span data-ttu-id="a937d-143">CompatiblePSEditions キーを使用するサンプルのモジュール マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="a937d-143">Sample module manifest file with CompatiblePSEditions key</span></span>

```powershell
@{
# - - -

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

# -- - -
}
```

#### <a name="module-contents"></a><span data-ttu-id="a937d-144">モジュールの内容</span><span class="sxs-lookup"><span data-stu-id="a937d-144">Module contents</span></span>

```powershell

PS C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions> dir -Recurse

    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/5/2016   1:37 PM                clr
d-----         7/5/2016   1:36 PM                coreclr
-a----         7/5/2016   1:34 PM           4906 ModuleWithEditions.psd1

    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\clr

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         7/5/2016   1:35 PM              0 MyFullClrNM1.dll
-a----         7/5/2016   1:35 PM              0 MyFullClrNM2.dll
-a----         7/5/2016   1:35 PM              0 MyFullClrRM.dl

    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\coreclr

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         7/5/2016   1:35 PM              0 MyCoreClrNM1.dll
-a----         7/5/2016   1:35 PM              0 MyCoreClrNM2.dll
-a----         7/5/2016   1:35 PM              0 MyCoreClrRM.dl
```

## <a name="powershell-gallery-users-can-find-the-list-of-modules-supported-on-a-specific-powershell-edition-using-tags-pseditiondesktop-and-pseditioncore"></a><span data-ttu-id="a937d-145">PowerShell ギャラリー ユーザーは、PSEdition_Desktop および PSEdition_Core タグを使用して特定の PowerShell エディションでサポートされているモジュールの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a937d-145">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags PSEdition_Desktop and PSEdition_Core.</span></span>
<span data-ttu-id="a937d-146">PSEdition_Desktop および PSEdition_Core タグがないモジュールは、PowerShell Desktop エディションで正常に動作するものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a937d-146">Modules without PSEdition_Desktop and PSEdition_Core tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell

# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEditon_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEditon_Core

```


## <a name="more-details"></a><span data-ttu-id="a937d-147">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a937d-147">More details</span></span>
### <a name="scripts-with-pseditionsscriptscriptwithpseditionsupportmd"></a>[<span data-ttu-id="a937d-148">PSEditions のスクリプト</span><span class="sxs-lookup"><span data-stu-id="a937d-148">Scripts with PSEditions</span></span>](../script/scriptwithpseditionsupport.md)
### <a name="pseditions-support-on-powershellgallerypsgallerypsgallerypseditionsmd"></a>[<span data-ttu-id="a937d-149">PowerShellGallery での PSEditions のサポート</span><span class="sxs-lookup"><span data-stu-id="a937d-149">PSEditions support on PowerShellGallery</span></span>](../../psgallery/psgallery_pseditions.md)
### <a name="update-module-manifest-psgetupdate-modulemanifestmd"></a><span data-ttu-id="a937d-150">[モジュール マニフェストを更新する] (./psget_update-modulemanifest.md)</span><span class="sxs-lookup"><span data-stu-id="a937d-150">[Update module manifest] (./psget_update-modulemanifest.md)</span></span>