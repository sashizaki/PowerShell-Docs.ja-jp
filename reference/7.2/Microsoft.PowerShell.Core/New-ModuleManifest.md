---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/02/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-modulemanifest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ModuleManifest
ms.openlocfilehash: 713c35b2f9f651d455ac08401aa1f7eb48676174
ms.sourcegitcommit: 04faa7dc1122bce839295d4891bd8b2f0ecb06ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "99599321"
---
# <span data-ttu-id="87435-102">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="87435-102">New-ModuleManifest</span></span>

## <span data-ttu-id="87435-103">概要</span><span class="sxs-lookup"><span data-stu-id="87435-103">SYNOPSIS</span></span>
<span data-ttu-id="87435-104">新しいモジュール マニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="87435-104">Creates a new module manifest.</span></span>

## <span data-ttu-id="87435-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="87435-105">SYNTAX</span></span>

### <span data-ttu-id="87435-106">すべて</span><span class="sxs-lookup"><span data-stu-id="87435-106">All</span></span>

```
New-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-PowerShellVersion <Version>] [-CLRVersion <Version>] [-DotNetFrameworkVersion <Version>]
 [-PowerShellHostName <String>] [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>]
 [-RequiredAssemblies <String[]>] [-FileList <String[]>] [-ModuleList <Object[]>]
 [-FunctionsToExport <String[]>] [-AliasesToExport <String[]>] [-VariablesToExport <String[]>]
 [-CmdletsToExport <String[]>] [-DscResourcesToExport <String[]>] [-CompatiblePSEditions <String[]>]
 [-PrivateData <Object>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ReleaseNotes <String>] [-Prerelease <String>] [-RequireLicenseAcceptance]
 [-ExternalModuleDependencies <String[]>] [-HelpInfoUri <String>] [-PassThru]
 [-DefaultCommandPrefix <String>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="87435-107">Description</span><span class="sxs-lookup"><span data-stu-id="87435-107">DESCRIPTION</span></span>

<span data-ttu-id="87435-108">この `New-ModuleManifest` コマンドレットは、新しいモジュールマニフェスト () ファイルを作成し `.psd1` 、その値を設定して、指定されたパスにマニフェストファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="87435-108">The `New-ModuleManifest` cmdlet creates a new module manifest (`.psd1`) file, populates its values, and saves the manifest file in the specified path.</span></span>

<span data-ttu-id="87435-109">モジュールの作成者は、このコマンドレットを使用して、モジュールのマニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="87435-109">Module authors can use this cmdlet to create a manifest for their module.</span></span> <span data-ttu-id="87435-110">モジュールマニフェストは、 `.psd1` ハッシュテーブルを含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="87435-110">A module manifest is a `.psd1` file that contains a hash table.</span></span> <span data-ttu-id="87435-111">モジュールの内容や属性について説明するハッシュ テーブル内のキーと値が、前提条件を定義し、コンポーネントの処理方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="87435-111">The keys and values in the hash table describe the contents and attributes of the module, define the prerequisites, and determine how the components are processed.</span></span> <span data-ttu-id="87435-112">モジュールにはマニフェストは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="87435-112">Manifests aren't required for a module.</span></span>

<span data-ttu-id="87435-113">`New-ModuleManifest` 共通に使用されるすべてのマニフェストキーを含むマニフェストを作成します。そのため、既定の出力をマニフェストテンプレートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-113">`New-ModuleManifest` creates a manifest that includes all the commonly used manifest keys, so you can use the default output as a manifest template.</span></span> <span data-ttu-id="87435-114">値を追加または変更したり、このコマンドレットでは追加されないモジュールキーを追加したりするには、結果のファイルをテキストエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="87435-114">To add or change values, or to add module keys that this cmdlet doesn't add, open the resulting file in a text editor.</span></span>

<span data-ttu-id="87435-115">**Path** および **PassThru** を除き、各パラメーターは、モジュールマニフェストキーとその値を作成します。</span><span class="sxs-lookup"><span data-stu-id="87435-115">Each parameter, except for **Path** and **PassThru**, creates a module manifest key and its value.</span></span>
<span data-ttu-id="87435-116">モジュール マニフェストでは、**ModuleVersion** キーのみが必須です。</span><span class="sxs-lookup"><span data-stu-id="87435-116">In a module manifest, only the **ModuleVersion** key is required.</span></span> <span data-ttu-id="87435-117">パラメーターの説明で指定されていない限り、コマンドからパラメーターを省略すると、によっ `New-ModuleManifest` て影響を与えることなく、関連付けられた値のコメント文字列がによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="87435-117">Unless specified in the parameter description, if you omit a parameter from the command, `New-ModuleManifest` creates a comment string for the associated value that has no effect.</span></span>

<span data-ttu-id="87435-118">PowerShell 2.0 では、では、 `New-ModuleManifest` 必須のパラメーター値に加えて、コマンドで指定されていない一般的に使用されるパラメーターの値を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="87435-118">In PowerShell 2.0, `New-ModuleManifest` prompts you for the values of commonly used parameters that aren't specified in the command, in addition to required parameter values.</span></span> <span data-ttu-id="87435-119">PowerShell 3.0 以降では、 `New-ModuleManifest` 必要なパラメーター値が指定されていない場合にのみプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87435-119">Beginning in PowerShell 3.0, `New-ModuleManifest` prompts only when required parameter values aren't specified.</span></span>

<span data-ttu-id="87435-120">PowerShell ギャラリーにモジュールを発行する予定の場合、マニフェストには特定のプロパティの値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="87435-120">If you are planning to publish your module in the PowerShell Gallery, the manifest must contain values for certain properties.</span></span> <span data-ttu-id="87435-121">詳細については、ギャラリーのドキュメントの「 [PowerShell ギャラリーに発行された項目に必要なメタデータ](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87435-121">For more information, see [Required metadata for items published to the PowerShell Gallery](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) in the Gallery documentation.</span></span>

## <span data-ttu-id="87435-122">例</span><span class="sxs-lookup"><span data-stu-id="87435-122">EXAMPLES</span></span>

### <span data-ttu-id="87435-123">例 1-新しいモジュールマニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="87435-123">Example 1 - Create a new module manifest</span></span>

<span data-ttu-id="87435-124">この例では、 **Path** パラメーターで指定したファイルに新しいモジュールマニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="87435-124">This example creates a new module manifest in the file that is specified by the **Path** parameter.</span></span>
<span data-ttu-id="87435-125">**PassThru** パラメーターは、出力をパイプラインとファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="87435-125">The **PassThru** parameter sends the output to the pipeline and to the file.</span></span>

<span data-ttu-id="87435-126">出力は、マニフェスト内のすべてのキーの既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="87435-126">The output shows the default values of all keys in the manifest.</span></span>

```powershell
New-ModuleManifest -Path C:\ps-test\Test-Module\Test-Module.psd1 -PassThru
```

```Output
#
# Module manifest for module 'Test-Module'
#
# Generated by: ContosoAdmin
#
# Generated on: 7/12/2019
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '0.0.1'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = 'e1826c6e-c420-4eef-9ac8-185e3669ca6a'

# Author of this module
Author = 'ContosoAdmin'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) ContosoAdmin. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module.
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export.
FunctionsToExport = @()

# Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export.
CmdletsToExport = @()

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export.
AliasesToExport = @()

# DSC resources to export from this module
# DscResourcesToExport = @()

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{

    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''

        # A URL to the main website for this project.
        # ProjectUri = ''

        # A URL to an icon representing this module.
        # IconUri = ''

        # ReleaseNotes of this module
        # ReleaseNotes = ''

        # Prerelease string of this module
        # Prerelease = ''

        # Flag to indicate whether the module requires explicit user acceptance for install/update/save
        # RequireLicenseAcceptance = $false

        # External dependent modules of this module
        # ExternalModuleDependencies = @()

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}
```

### <span data-ttu-id="87435-127">例 2-いくつかの事前設定される設定を使用して新しいマニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="87435-127">Example 2 - Create a new manifest with some prepopulated settings</span></span>

<span data-ttu-id="87435-128">この例では、新しいモジュールマニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="87435-128">This example creates a new module manifest.</span></span> <span data-ttu-id="87435-129">**PowerShellVersion** および **AliasesToExport**　パラメーターを使用して、値を対応するマニフェスト キーに追加します。</span><span class="sxs-lookup"><span data-stu-id="87435-129">It uses the **PowerShellVersion** and **AliasesToExport** parameters to add values to the corresponding manifest keys.</span></span>

```powershell
New-ModuleManifest -PowerShellVersion 1.0 -AliasesToExport JKBC, DRC, TAC -Path C:\ps-test\ManifestTest.psd1
```

### <span data-ttu-id="87435-130">例 3-他のモジュールを必要とするマニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="87435-130">Example 3 - Create a manifest that requires other modules</span></span>

<span data-ttu-id="87435-131">この例では、文字列形式を使用して **BitsTransfer** モジュールの名前を指定し、ハッシュテーブル形式を使用して、 **psscheduledjob** モジュールの名前、 **GUID**、およびバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-131">This example uses a string format to specify the name of the **BitsTransfer** module and the hash table format to specify the name, a **GUID**, and a version of the **PSScheduledJob** module.</span></span>

```powershell
$moduleSettings = @{
  RequiredModules = ("BitsTransfer", @{
    ModuleName="PSScheduledJob"
    ModuleVersion="1.0.0.0";
    GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"
  })
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="87435-132">この例では、 **Modulelist**、 **RequiredModules**、および **nestedmodules** パラメーターの文字列形式とハッシュテーブル形式を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="87435-132">This example shows how to use the string and hash table formats of the **ModuleList**, **RequiredModules**, and **NestedModules** parameter.</span></span> <span data-ttu-id="87435-133">同じパラメーター値に、文字列とハッシュ テーブルを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="87435-133">You can combine strings and hash tables in the same parameter value.</span></span>

### <span data-ttu-id="87435-134">例 4-更新可能なヘルプをサポートするマニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="87435-134">Example 4 - Create a manifest that supports updateable help</span></span>

<span data-ttu-id="87435-135">この例では、 **helpinfouri** パラメーターを使用して、モジュールマニフェストに **helpinfouri** キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="87435-135">This example uses the **HelpInfoUri** parameter to create a **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="87435-136">パラメーターの値とキーは、 **http** または **https** で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="87435-136">The value of the parameter and the key must begin with **http** or **https**.</span></span> <span data-ttu-id="87435-137">この値は、モジュールの HelpInfo XML 更新可能なヘルプの情報ファイルを検索するための更新可能なヘルプ システムを示しています。</span><span class="sxs-lookup"><span data-stu-id="87435-137">This value tells the Updatable Help system where to find the HelpInfo XML updatable help information file for the module.</span></span>

```powershell
$moduleSettings = @{
  HelpInfoUri = 'http://https://go.microsoft.com/fwlink/?LinkID=603'
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="87435-138">更新可能なヘルプの詳細については、「 [about_Updatable_Help](./About/about_Updatable_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87435-138">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="87435-139">HelpInfo XML ファイルの詳細については、「 [更新可能なヘルプのサポート](/powershell/scripting/developer/module/supporting-updatable-help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87435-139">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

### <span data-ttu-id="87435-140">例 5-モジュール情報を取得する</span><span class="sxs-lookup"><span data-stu-id="87435-140">Example 5 - Getting module information</span></span>

<span data-ttu-id="87435-141">この例では、モジュールの構成値を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="87435-141">This example shows how to get the configuration values of a module.</span></span> <span data-ttu-id="87435-142">モジュールマニフェスト内の値は、モジュールオブジェクトのプロパティの値に反映されます。</span><span class="sxs-lookup"><span data-stu-id="87435-142">The values in the module manifest are reflected in the values of properties of the module object.</span></span>

<span data-ttu-id="87435-143">`Get-Module`コマンドレットを使用して、 **List** パラメーターを使用して、 **PowerShell 診断** モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="87435-143">The `Get-Module` cmdlet is used to get the **Microsoft.PowerShell.Diagnostics** module using the **List** parameter.</span></span> <span data-ttu-id="87435-144">このコマンドは、モジュールをコマンドレットに送信して、 `Format-List` モジュールオブジェクトのすべてのプロパティと値を表示します。</span><span class="sxs-lookup"><span data-stu-id="87435-144">The command sends the module to the `Format-List` cmdlet to display all properties and values of the module object.</span></span>

```powershell
Get-Module Microsoft.PowerShell.Diagnostics -List | Format-List -Property *
```

```Output
LogPipelineExecutionDetails : False
Name                        : Microsoft.PowerShell.Diagnostics
Path                        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics\Micro
                              soft.PowerShell.Diagnostics.psd1
Definition                  :
Description                 :
Guid                        : ca046f10-ca64-4740-8ff9-2565dba61a4f
HelpInfoUri                 : https://go.microsoft.com/fwlink/?LinkID=210596
ModuleBase                  : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics
PrivateData                 :
Version                     : 3.0.0.0
ModuleType                  : Manifest
Author                      : Microsoft Corporation
AccessMode                  : ReadWrite
ClrVersion                  : 4.0
CompanyName                 : Microsoft Corporation
Copyright                   : Microsoft Corporation. All rights reserved.
DotNetFrameworkVersion      :
ExportedFunctions           : {}
ExportedCmdlets             : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
ExportedCommands            : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
FileList                    : {}
ModuleList                  : {}
NestedModules               : {}
PowerShellHostName          :
PowerShellHostVersion       :
PowerShellVersion           : 3.0
ProcessorArchitecture       : None
Scripts                     : {}
RequiredAssemblies          : {}
RequiredModules             : {}
RootModule                  :
ExportedVariables           : {}
ExportedAliases             : {}
ExportedWorkflows           : {}
SessionState                :
OnRemove                    :
ExportedFormatFiles         : {C:\Windows\system32\WindowsPowerShell\v1.0\Event.format.ps1xml,
                              C:\Windows\system32\WindowsPowerShell\v1.0\Diagnostics.format.ps1xml}
ExportedTypeFiles           : {C:\Windows\system32\WindowsPowerShell\v1.0\GetEvent.types.ps1xml}
```

## <span data-ttu-id="87435-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="87435-145">PARAMETERS</span></span>

### <span data-ttu-id="87435-146">-Aseasestoexport</span><span class="sxs-lookup"><span data-stu-id="87435-146">-AliasesToExport</span></span>

<span data-ttu-id="87435-147">モジュールがエクスポートするエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-147">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="87435-148">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-148">Wildcards are permitted.</span></span>

<span data-ttu-id="87435-149">このパラメーターを使用して、モジュールによってエクスポートされるエイリアスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="87435-149">You can use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="87435-150">エクスポートされたエイリアスの一覧からエイリアスを削除できますが、一覧にエイリアスを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="87435-150">It can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

<span data-ttu-id="87435-151">このパラメーターを省略した場合は、によって、 `New-ModuleManifest`  `*` モジュールで定義されているすべてのエイリアスがマニフェストによってエクスポートされることを示す値 (all) を使用して、指定されたキーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87435-151">If you omit this parameter, `New-ModuleManifest` creates an **AliasesToExport** key with a value of `*` (all), meaning that all aliases defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="87435-152">-作成者</span><span class="sxs-lookup"><span data-stu-id="87435-152">-Author</span></span>

<span data-ttu-id="87435-153">モジュールの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-153">Specifies the module author.</span></span>

<span data-ttu-id="87435-154">このパラメーターを省略すると、では、 `New-ModuleManifest` 現在のユーザーの名前を使用して **作成者** キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87435-154">If you omit this parameter, `New-ModuleManifest` creates an **Author** key with the name of the current user.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Name of the current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-155">-///エクスポート</span><span class="sxs-lookup"><span data-stu-id="87435-155">-CmdletsToExport</span></span>

<span data-ttu-id="87435-156">モジュールがエクスポートするコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-156">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="87435-157">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-157">Wildcards are permitted.</span></span>

<span data-ttu-id="87435-158">このパラメーターを使用して、モジュールによってエクスポートされるコマンドレットを制限できます。</span><span class="sxs-lookup"><span data-stu-id="87435-158">You can use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="87435-159">エクスポートされたコマンドレットの一覧からコマンドレットを削除できますが、一覧にコマンドレットを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="87435-159">It can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

<span data-ttu-id="87435-160">このパラメーターを省略すると、によって、 `New-ModuleManifest` モジュールで定義されているすべてのコマンドレットがマニフェストによってエクスポートされることを意味する、(すべて) の値を持つコマンドレット **stoexport** キーが作成さ `*` れます。</span><span class="sxs-lookup"><span data-stu-id="87435-160">If you omit this parameter, `New-ModuleManifest` creates a **CmdletsToExport** key with a value of `*` (all), meaning that all cmdlets defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="87435-161">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="87435-161">-CompanyName</span></span>

<span data-ttu-id="87435-162">モジュールを作成した企業またはベンダーを識別します。</span><span class="sxs-lookup"><span data-stu-id="87435-162">Identifies the company or vendor who created the module.</span></span>

<span data-ttu-id="87435-163">このパラメーターを省略した場合、では、 `New-ModuleManifest` "Unknown" という値を持つ **CompanyName** キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87435-163">If you omit this parameter, `New-ModuleManifest` creates a **CompanyName** key with a value of "Unknown".</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "Unknown"
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-164">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="87435-164">-CompatiblePSEditions</span></span>

<span data-ttu-id="87435-165">モジュールの互換性のある PSEditions を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-165">Specifies the module's compatible PSEditions.</span></span> <span data-ttu-id="87435-166">PSEdition の詳細については、「 [モジュールと互換性のある PowerShell のエディション](/powershell/scripting/gallery/concepts/module-psedition-support)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87435-166">For information about PSEdition, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-167">-Copyright</span><span class="sxs-lookup"><span data-stu-id="87435-167">-Copyright</span></span>

<span data-ttu-id="87435-168">モジュールの著作権表記を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-168">Specifies a copyright statement for the module.</span></span>

<span data-ttu-id="87435-169">このパラメーターを省略すると、では、 `New-ModuleManifest` 値がの **著作権** キーが作成され `(c) <year> <username>. All rights reserved.` ます。ここで、 `<year>` は現在の年、 `<username>` は **Author** キーの値です。</span><span class="sxs-lookup"><span data-stu-id="87435-169">If you omit this parameter, `New-ModuleManifest` creates a **Copyright** key with a value of `(c) <year> <username>. All rights reserved.` where `<year>` is the current year and `<username>` is the value of the **Author** key.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (c) <year> <username>. All rights reserved.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-170">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="87435-170">-DefaultCommandPrefix</span></span>

<span data-ttu-id="87435-171">セッションにインポートするときに、モジュール内のすべてのコマンドの名詞の前に付加されるプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-171">Specifies a prefix that is prepended to the nouns of all commands in the module when they're imported into a session.</span></span> <span data-ttu-id="87435-172">プレフィックス文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-172">Enter a prefix string.</span></span> <span data-ttu-id="87435-173">プレフィックスは、ユーザーのセッションでのコマンド名の競合を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="87435-173">Prefixes prevent command name conflicts in a user's session.</span></span>

<span data-ttu-id="87435-174">モジュールユーザーは、コマンドレットの **prefix** パラメーターを指定することによって、このプレフィックスをオーバーライドでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="87435-174">Module users can override this prefix by specifying the **Prefix** parameter of the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="87435-175">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="87435-175">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="87435-176">-Description</span><span class="sxs-lookup"><span data-stu-id="87435-176">-Description</span></span>

<span data-ttu-id="87435-177">モジュールの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="87435-177">Describes the contents of the module.</span></span>

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

### <span data-ttu-id="87435-178">-DotNetFrameworkVersion</span><span class="sxs-lookup"><span data-stu-id="87435-178">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="87435-179">モジュールに必要な、Microsoft .NET Framework の最低限のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-179">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-180">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="87435-180">-DscResourcesToExport</span></span>

<span data-ttu-id="87435-181">モジュールによってエクスポートされる Desired State Configuration (DSC) リソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-181">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="87435-182">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-182">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="87435-183">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="87435-183">-ExternalModuleDependencies</span></span>

<span data-ttu-id="87435-184">このモジュールが依存している外部モジュールの一覧。</span><span class="sxs-lookup"><span data-stu-id="87435-184">A list of external modules that this module is depends on.</span></span>

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

### <span data-ttu-id="87435-185">-FileList</span><span class="sxs-lookup"><span data-stu-id="87435-185">-FileList</span></span>

<span data-ttu-id="87435-186">モジュールに含まれているすべての項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-186">Specifies all items that are included in the module.</span></span>

<span data-ttu-id="87435-187">このキーは、モジュール インベントリとしての動作を想定して設計されています。</span><span class="sxs-lookup"><span data-stu-id="87435-187">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="87435-188">このキーに記載されているファイルはモジュールの発行時に含まれますが、すべての関数は自動的にエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="87435-188">The files listed in the key are included when the module is published, but any functions aren't automatically exported.</span></span>

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

### <span data-ttu-id="87435-189">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="87435-189">-FormatsToProcess</span></span>

<span data-ttu-id="87435-190">`.ps1xml`モジュールのインポート時に実行される書式設定ファイル () を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-190">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="87435-191">モジュールをインポートすると、PowerShell は `Update-FormatData` 指定されたファイルを使用してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="87435-191">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="87435-192">書式設定ファイルはスコープが設定されていないため、セッションのすべてのセッション状態に影響します。</span><span class="sxs-lookup"><span data-stu-id="87435-192">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="87435-193">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="87435-193">-FunctionsToExport</span></span>

<span data-ttu-id="87435-194">モジュールがエクスポートする関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-194">Specifies the functions that the module exports.</span></span> <span data-ttu-id="87435-195">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-195">Wildcards are permitted.</span></span>

<span data-ttu-id="87435-196">このパラメーターを使用して、モジュールによってエクスポートされる関数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="87435-196">You can use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="87435-197">エクスポートされたエイリアスの一覧から関数を削除できますが、一覧に関数を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="87435-197">It can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

<span data-ttu-id="87435-198">このパラメーターを省略した場合、に `New-ModuleManifest` よって **Functionstoexport** キーが作成されます。これは、 `*` モジュールで定義されているすべての関数がマニフェストによってエクスポートされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="87435-198">If you omit this parameter, `New-ModuleManifest` creates an **FunctionsToExport** key with a value of `*` (all), meaning that all functions defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="87435-199">-Guid</span><span class="sxs-lookup"><span data-stu-id="87435-199">-Guid</span></span>

<span data-ttu-id="87435-200">モジュールの一意の識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-200">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="87435-201">**GUID** は、同じ名前のモジュールを区別するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-201">The **GUID** can be used to distinguish among modules with the same name.</span></span>

<span data-ttu-id="87435-202">このパラメーターを省略すると、は `New-ModuleManifest` マニフェストに **guid** キーを作成し、値の **guid** を生成します。</span><span class="sxs-lookup"><span data-stu-id="87435-202">If you omit this parameter, `New-ModuleManifest` creates a **GUID** key in the manifest and generates a **GUID** for the value.</span></span>

<span data-ttu-id="87435-203">PowerShell で新しい **GUID** を作成するには、「」と入力 `[guid]::NewGuid()` します。</span><span class="sxs-lookup"><span data-stu-id="87435-203">To create a new **GUID** in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A GUID generated for the module
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-204">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="87435-204">-HelpInfoUri</span></span>

<span data-ttu-id="87435-205">モジュールの HelpInfo XML ファイルのインターネットアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-205">Specifies the internet address of the HelpInfo XML file for the module.</span></span> <span data-ttu-id="87435-206">**Http** または **https** で始まる Uniform Resource Identifier (URI) を入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-206">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https**.</span></span>

<span data-ttu-id="87435-207">HelpInfo XML ファイルは、PowerShell 3.0 で導入された更新可能なヘルプ機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="87435-207">The HelpInfo XML file supports the Updatable Help feature that was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="87435-208">これには、モジュールのダウンロード可能なヘルプ ファイルの場所、およびサポートされている各ロケールの最新のヘルプ ファイルのバージョン番号に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="87435-208">It contains information about the location of downloadable help files for the module and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="87435-209">更新可能なヘルプの詳細については、「 [about_Updatable_Help](./About/about_Updatable_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87435-209">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="87435-210">HelpInfo XML ファイルの詳細については、「 [更新可能なヘルプのサポート](/powershell/scripting/developer/module/supporting-updatable-help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87435-210">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="87435-211">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="87435-211">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="87435-212">-IconUri</span><span class="sxs-lookup"><span data-stu-id="87435-212">-IconUri</span></span>

<span data-ttu-id="87435-213">モジュールのアイコンの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-213">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="87435-214">指定されたアイコンは、モジュールのギャラリー web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="87435-214">The specified icon is displayed on the gallery web page for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-215">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="87435-215">-LicenseUri</span></span>

<span data-ttu-id="87435-216">モジュールのライセンス条項の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-216">Specifies the URL of licensing terms for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-217">-ModuleList</span><span class="sxs-lookup"><span data-stu-id="87435-217">-ModuleList</span></span>

<span data-ttu-id="87435-218">このモジュールに含まれているすべてのモジュールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="87435-218">Lists all modules that are included in this module.</span></span>

<span data-ttu-id="87435-219">各モジュールの名前を文字列として、または **ModuleName**　キーと **ModuleVersion** キーを含むハッシュ テーブルとして入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-219">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="87435-220">ハッシュ テーブルは、オプションの **GUID** キーも保持できます。</span><span class="sxs-lookup"><span data-stu-id="87435-220">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="87435-221">パラメーター値として文字列とハッシュ テーブルを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="87435-221">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="87435-222">このキーは、モジュール インベントリとしての動作を想定して設計されています。</span><span class="sxs-lookup"><span data-stu-id="87435-222">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="87435-223">このキーの値に示されているモジュールは自動的に処理されません。</span><span class="sxs-lookup"><span data-stu-id="87435-223">The modules that are listed in the value of this key aren't automatically processed.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-224">-ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="87435-224">-ModuleVersion</span></span>

<span data-ttu-id="87435-225">モジュールのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-225">Specifies the module's version.</span></span>

<span data-ttu-id="87435-226">このパラメーターは必須ではありませんが、マニフェストには **ModuleVersion** キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="87435-226">This parameter isn't required, but a **ModuleVersion** key is required in the manifest.</span></span> <span data-ttu-id="87435-227">このパラメーターを省略すると、では、 `New-ModuleManifest` 値が1.0 の **ModuleVersion** キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87435-227">If you omit this parameter, `New-ModuleManifest` creates a **ModuleVersion** key with a value of 1.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1.0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-228">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="87435-228">-NestedModules</span></span>

<span data-ttu-id="87435-229">`.psm1` `.dll` モジュールのセッション状態にインポートされるスクリプトモジュール () とバイナリモジュール () を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-229">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="87435-230">**Nestedmodules** キー内のファイルは、値に示されている順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="87435-230">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="87435-231">各モジュールの名前を文字列として、または **ModuleName**　キーと **ModuleVersion** キーを含むハッシュ テーブルとして入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-231">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="87435-232">ハッシュ テーブルは、オプションの **GUID** キーも保持できます。</span><span class="sxs-lookup"><span data-stu-id="87435-232">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="87435-233">パラメーター値として文字列とハッシュ テーブルを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="87435-233">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="87435-234">通常、入れ子になったモジュールには、ルート モジュールが内部処理のために必要とするコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87435-234">Typically, nested modules contain commands that the root module needs for its internal processing.</span></span>
<span data-ttu-id="87435-235">既定では、入れ子になったモジュール内のコマンドは、モジュールのセッション状態から呼び出し元のセッション状態にエクスポートされますが、ルートモジュールは、エクスポートするコマンドを制限できます。</span><span class="sxs-lookup"><span data-stu-id="87435-235">By default, the commands in nested modules are exported from the module's session state into the caller's session state, but the root module can restrict the commands that it exports.</span></span> <span data-ttu-id="87435-236">たとえば、コマンドを使用し `Export-ModuleMember` ます。</span><span class="sxs-lookup"><span data-stu-id="87435-236">For example, by using an `Export-ModuleMember` command.</span></span>

<span data-ttu-id="87435-237">モジュールセッション状態の入れ子になったモジュールは、ルートモジュールで使用できますが、 `Get-Module` 呼び出し元のセッション状態のコマンドからは返されません。</span><span class="sxs-lookup"><span data-stu-id="87435-237">Nested modules in the module session state are available to the root module, but they aren't returned by a `Get-Module` command in the caller's session state.</span></span>

<span data-ttu-id="87435-238">`.ps1` **Nestedmodules** キーに記載されているスクリプト () は、呼び出し元のセッション状態ではなく、モジュールのセッション状態で実行されます。</span><span class="sxs-lookup"><span data-stu-id="87435-238">Scripts (`.ps1`) that are listed in the **NestedModules** key are run in the module's session state, not in the caller's session state.</span></span> <span data-ttu-id="87435-239">呼び出し元のセッション状態でスクリプトを実行するには、マニフェストの **ScriptsToProcess** キーの値にスクリプト ファイル名を列挙します。</span><span class="sxs-lookup"><span data-stu-id="87435-239">To run a script in the caller's session state, list the script file name in the value of the **ScriptsToProcess** key in the manifest.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-240">-PassThru</span><span class="sxs-lookup"><span data-stu-id="87435-240">-PassThru</span></span>

<span data-ttu-id="87435-241">結果のモジュールマニフェストをコンソールに書き込み、ファイルを作成し `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="87435-241">Writes the resulting module manifest to the console and creates a `.psd1` file.</span></span> <span data-ttu-id="87435-242">既定では、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="87435-242">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="87435-243">-Path</span><span class="sxs-lookup"><span data-stu-id="87435-243">-Path</span></span>

<span data-ttu-id="87435-244">新しいモジュール マニフェストのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-244">Specifies the path and file name of the new module manifest.</span></span> <span data-ttu-id="87435-245">ファイル名拡張子の付いたパスとファイル名を入力し `.psd1` ます。たとえば、のように `$pshome\Modules\MyModule\MyModule.psd1` なります。</span><span class="sxs-lookup"><span data-stu-id="87435-245">Enter a path and file name with a `.psd1` file name extension, such as `$pshome\Modules\MyModule\MyModule.psd1`.</span></span> <span data-ttu-id="87435-246">**Path** パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="87435-246">The **Path** parameter is required.</span></span>

<span data-ttu-id="87435-247">既存のファイルへのパスを指定すると、ファイルに `New-ModuleManifest` 読み取り専用属性が含まれていない限り、は警告なしでファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="87435-247">If you specify the path to an existing file, `New-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="87435-248">マニフェストはモジュールのディレクトリに配置する必要があります。マニフェストファイル名はモジュールディレクトリ名と同じである必要がありますが、 `.psd1` ファイル名拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="87435-248">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` file name extension.</span></span>

> [!NOTE]
> <span data-ttu-id="87435-249">`$PSHOME` `$HOME` **パス** パラメーター値のプロンプトに応答して、やなどの変数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="87435-249">You cannot use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="87435-250">変数を使用するには、コマンドに **Path** パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="87435-250">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-251">-PowerShellHostName</span><span class="sxs-lookup"><span data-stu-id="87435-251">-PowerShellHostName</span></span>

<span data-ttu-id="87435-252">モジュールに必要な PowerShell ホストプログラムの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-252">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="87435-253">ホストプログラムの名前 ( **Windows PowerShell ISE host** や **consolehost** など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-253">Enter the name of the host program, such as **Windows PowerShell ISE Host** or **ConsoleHost**.</span></span> <span data-ttu-id="87435-254">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="87435-254">Wildcards aren't permitted.</span></span>

<span data-ttu-id="87435-255">ホストプログラムの名前を検索するには、プログラムで「」と入力 `$Host.Name` します。</span><span class="sxs-lookup"><span data-stu-id="87435-255">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="87435-256">-PowerShellHostVersion</span><span class="sxs-lookup"><span data-stu-id="87435-256">-PowerShellHostVersion</span></span>

<span data-ttu-id="87435-257">モジュールで動作する PowerShell ホストプログラムの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-257">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="87435-258">1.1 などのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-258">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-259">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="87435-259">-PowerShellVersion</span></span>

<span data-ttu-id="87435-260">このモジュールで動作する PowerShell の最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-260">Specifies the minimum version of PowerShell that works with this module.</span></span> <span data-ttu-id="87435-261">たとえば、パラメーターの値として1.0、2.0、または3.0 を入力できます。</span><span class="sxs-lookup"><span data-stu-id="87435-261">For example, you can enter 1.0, 2.0, or 3.0 as the parameter's value.</span></span> <span data-ttu-id="87435-262">これは、X. X 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="87435-262">It must be in an X.X format.</span></span> <span data-ttu-id="87435-263">たとえば、を送信すると、 `5` PowerShell によってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="87435-263">For example, if you submit `5`, PowerShell will throw an error.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-264">-プレリリース</span><span class="sxs-lookup"><span data-stu-id="87435-264">-Prerelease</span></span>

<span data-ttu-id="87435-265">このモジュールのプレリリース文字列。</span><span class="sxs-lookup"><span data-stu-id="87435-265">Prerelease string of this module.</span></span> <span data-ttu-id="87435-266">プレリリース文字列を追加すると、モジュールがプレリリースバージョンとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="87435-266">Adding a Prerelease string identifies the module as a prerelease version.</span></span> <span data-ttu-id="87435-267">モジュールが PowerShell ギャラリーに発行されると、このデータを使用してプレリリースパッケージが識別されます。</span><span class="sxs-lookup"><span data-stu-id="87435-267">When the module is published to the PowerShell Gallery, this data is used to identify prerelease packages.</span></span> <span data-ttu-id="87435-268">ギャラリーからプレリリースパッケージを取得するには、PowerShellGet コマンド、、、およびを指定して **allowprerelease リリース** パラメーターを使用する必要があり `Find-Module` `Install-Module` `Update-Module` `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="87435-268">To acquire prerelease packages from the Gallery, you must use the **AllowPrerelease** parameter with the PowerShellGet commands `Find-Module`, `Install-Module`, `Update-Module`, and `Save-Module`.</span></span>

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

### <span data-ttu-id="87435-269">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="87435-269">-PrivateData</span></span>

<span data-ttu-id="87435-270">インポート時にモジュールに渡されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-270">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-271">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="87435-271">-ProcessorArchitecture</span></span>

<span data-ttu-id="87435-272">モジュールに必要なプロセッサ アーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-272">Specifies the processor architecture that the module requires.</span></span> <span data-ttu-id="87435-273">有効な値は、x86、AMD64、IA64、MSIL、および None (不明または未指定) です。</span><span class="sxs-lookup"><span data-stu-id="87435-273">Valid values are x86, AMD64, IA64, MSIL, and None (unknown or unspecified).</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-274">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="87435-274">-ProjectUri</span></span>

<span data-ttu-id="87435-275">このプロジェクトについての web ページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-275">Specifies the URL of a web page about this project.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-276">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="87435-276">-ReleaseNotes</span></span>

<span data-ttu-id="87435-277">リリースノートを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-277">Specifies release notes.</span></span>

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

### <span data-ttu-id="87435-278">-RequiredAssemblies</span><span class="sxs-lookup"><span data-stu-id="87435-278">-RequiredAssemblies</span></span>

<span data-ttu-id="87435-279">モジュールに必要なアセンブリ () ファイルを指定し `.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="87435-279">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="87435-280">アセンブリ ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-280">Enter the assembly file names.</span></span>
<span data-ttu-id="87435-281">PowerShell は、型または形式を更新する前、入れ子になったモジュールをインポートする前、または **RootModule** キーの値に指定されているモジュールファイルをインポートする前に、指定されたアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="87435-281">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="87435-282">このパラメーターを使用して、アセンブリが **NestedModules** キーでバイナリ モジュールとして列挙されている場合でも、**FormatsToProcess** キーまたは **TypesToProcess** キーに列挙される形式または型ファイルを更新するために読み込む必要があるアセンブリを含め、モジュールに必要なすべてのアセンブリを列挙できます。</span><span class="sxs-lookup"><span data-stu-id="87435-282">Use this parameter to list all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="87435-283">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="87435-283">-RequiredModules</span></span>

<span data-ttu-id="87435-284">グローバル セッション状態にする必要があるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-284">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="87435-285">必要なモジュールがグローバルセッション状態でない場合は、PowerShell によってインポートされます。</span><span class="sxs-lookup"><span data-stu-id="87435-285">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="87435-286">必要なモジュールが使用できない場合、 `Import-Module` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="87435-286">If the required modules aren't available, the `Import-Module` command fails.</span></span>

<span data-ttu-id="87435-287">各モジュールの名前を文字列として、または **ModuleName**　キーと **ModuleVersion** キーを含むハッシュ テーブルとして入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-287">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="87435-288">ハッシュ テーブルは、オプションの **GUID** キーも保持できます。</span><span class="sxs-lookup"><span data-stu-id="87435-288">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="87435-289">パラメーター値として文字列とハッシュ テーブルを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="87435-289">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="87435-290">PowerShell 2.0 では、は `Import-Module` 必要なモジュールを自動的にインポートしません。</span><span class="sxs-lookup"><span data-stu-id="87435-290">In PowerShell 2.0, `Import-Module` doesn't import required modules automatically.</span></span> <span data-ttu-id="87435-291">必要なモジュールがグローバル セッション状態であることを確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="87435-291">It just verifies that the required modules are in the global session state.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-292">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="87435-292">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="87435-293">モジュールがインストール、更新、または保存のために明示的なユーザー受け入れを必要とするかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="87435-293">Flag to indicate whether the module requires explicit user acceptance for install, update, orsave.</span></span>

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

### <span data-ttu-id="87435-294">-RootModule</span><span class="sxs-lookup"><span data-stu-id="87435-294">-RootModule</span></span>

<span data-ttu-id="87435-295">モジュールのプライマリファイルまたはルートファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-295">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="87435-296">スクリプト ( `.ps1` )、スクリプトモジュール ( `.psm1` )、モジュールマニフェスト ( `.psd1` )、アセンブリ ( `.dll` )、コマンドレット定義 XML ファイル ()、 `.cdxml` またはワークフロー ( `.xaml` ) のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="87435-296">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest(`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="87435-297">モジュールのインポート時に、ルート モジュール ファイルからエクスポートされるメンバーは、呼び出し元のセッション状態にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="87435-297">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="87435-298">モジュールにマニフェストファイルがあり、 **RootModule** キーでルートファイルが指定されていない場合、マニフェストはモジュールのプライマリファイルになり、モジュールはマニフェストモジュール (ModuleType = manifest) になります。</span><span class="sxs-lookup"><span data-stu-id="87435-298">If a module has a manifest file and no root file was designated in the **RootModule** key, the manifest becomes the primary file for the module, and the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="87435-299">マニフェストを持つモジュール内のまたはファイルからメンバーをエクスポートするに `.psm1` は、 `.dll` マニフェスト内の **RootModule** または **nestedmodules** キーの値でこれらのファイルの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87435-299">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="87435-300">それ以外の場合、メンバーはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="87435-300">Otherwise, their members aren't exported.</span></span>

> [!NOTE]
> <span data-ttu-id="87435-301">PowerShell 2.0 では、このキーは **ModuleToProcess** と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="87435-301">In PowerShell 2.0, this key was called **ModuleToProcess**.</span></span> <span data-ttu-id="87435-302">**RootModule** パラメーター名またはその **ModuleToProcess** エイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-302">You can use the **RootModule** parameter name or its **ModuleToProcess** alias.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ModuleToProcess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-303">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="87435-303">-ScriptsToProcess</span></span>

<span data-ttu-id="87435-304">`.ps1`モジュールをインポートするときに、呼び出し元のセッション状態で実行されるスクリプト () ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-304">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="87435-305">ログイン スクリプトを使用する場合と同様に、これらのスクリプトを使用して、環境を準備できます。</span><span class="sxs-lookup"><span data-stu-id="87435-305">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="87435-306">モジュールのセッション状態で実行するスクリプトを指定するには、**NestedModules** キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="87435-306">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="87435-307">-タグ</span><span class="sxs-lookup"><span data-stu-id="87435-307">-Tags</span></span>

<span data-ttu-id="87435-308">タグの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-308">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="87435-309">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="87435-309">-TypesToProcess</span></span>

<span data-ttu-id="87435-310">`.ps1xml`モジュールをインポートするときに実行される型ファイル () を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-310">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="87435-311">モジュールをインポートすると、PowerShell は `Update-TypeData` 指定されたファイルを使用してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="87435-311">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="87435-312">型ファイルはスコープが設定されていないため、セッションのすべてのセッション状態に影響します。</span><span class="sxs-lookup"><span data-stu-id="87435-312">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="87435-313">-変数 Stoexport</span><span class="sxs-lookup"><span data-stu-id="87435-313">-VariablesToExport</span></span>

<span data-ttu-id="87435-314">モジュールがエクスポートする変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-314">Specifies the variables that the module exports.</span></span> <span data-ttu-id="87435-315">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87435-315">Wildcards are permitted.</span></span>

<span data-ttu-id="87435-316">このパラメーターを使用して、モジュールによってエクスポートされる変数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="87435-316">You can use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="87435-317">エクスポートされた変数の一覧から変数を削除することはできますが、一覧に変数を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="87435-317">It can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

<span data-ttu-id="87435-318">このパラメーターを省略した場合、によって、 `New-ModuleManifest` (all) の値を持つ変数 **stoexport** キーが作成され `*` ます。これは、モジュールで定義されているすべての変数がマニフェストによってエクスポートされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="87435-318">If you omit this parameter, `New-ModuleManifest` creates a **VariablesToExport** key with a value of `*` (all), meaning that all variables defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="87435-319">-Confirm</span><span class="sxs-lookup"><span data-stu-id="87435-319">-Confirm</span></span>

<span data-ttu-id="87435-320">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87435-320">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-321">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="87435-321">-WhatIf</span></span>

<span data-ttu-id="87435-322">が実行された場合に何が起こるか `New-ModuleManifest` を示します。</span><span class="sxs-lookup"><span data-stu-id="87435-322">Shows what would happen if `New-ModuleManifest` runs.</span></span> <span data-ttu-id="87435-323">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="87435-323">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-324">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="87435-324">-ClrVersion</span></span>

<span data-ttu-id="87435-325">モジュールに必要な、Microsoft .NET Framework の共通言語ランタイム (CLR) の最低限のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="87435-325">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87435-326">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="87435-326">CommonParameters</span></span>
<span data-ttu-id="87435-327">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="87435-327">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="87435-328">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87435-328">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="87435-329">入力</span><span class="sxs-lookup"><span data-stu-id="87435-329">INPUTS</span></span>

### <span data-ttu-id="87435-330">なし</span><span class="sxs-lookup"><span data-stu-id="87435-330">None</span></span>

<span data-ttu-id="87435-331">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="87435-331">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="87435-332">出力</span><span class="sxs-lookup"><span data-stu-id="87435-332">OUTPUTS</span></span>

### <span data-ttu-id="87435-333">None または System.String</span><span class="sxs-lookup"><span data-stu-id="87435-333">None or System.String</span></span>

<span data-ttu-id="87435-334">既定では、は `New-ModuleManifest` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="87435-334">By default, `New-ModuleManifest` doesn't generate any output.</span></span> <span data-ttu-id="87435-335">ただし、 **PassThru** パラメーターを使用すると、モジュールマニフェストを表す **system.string** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="87435-335">However, if you use the **PassThru** parameter, it generates a **System.String** object representing the module manifest.</span></span>

## <span data-ttu-id="87435-336">注</span><span class="sxs-lookup"><span data-stu-id="87435-336">NOTES</span></span>

<span data-ttu-id="87435-337">`New-ModuleManifest` Windows プラットフォームおよび Windows 以外のプラットフォームでを実行すると、 `.psd1` **UTF8NoBOM** としてエンコードされたモジュールマニフェスト () ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87435-337">`New-ModuleManifest` running on Windows and non-Windows platforms creates module manifest (`.psd1`) files encoded as **UTF8NoBOM**.</span></span>

<span data-ttu-id="87435-338">モジュール マニフェストは、通常、オプションです。</span><span class="sxs-lookup"><span data-stu-id="87435-338">Module manifests are usually optional.</span></span> <span data-ttu-id="87435-339">ただし、モジュール マニフェストは、グローバル アセンブリ キャッシュにインストールされているアセンブリをエクスポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="87435-339">However, a module manifest is required to export an assembly that is installed in the global assembly cache.</span></span>

<span data-ttu-id="87435-340">ディレクトリ内のファイルを追加または変更するには、 `$pshome\Modules` [ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="87435-340">To add or change files in the `$pshome\Modules` directory, start PowerShell with the **Run as administrator** option.</span></span>

> [!NOTE]
> <span data-ttu-id="87435-341">PowerShell 6.2 以降では、PowerShell はモジュールマニフェストの **FileList** プロパティに一覧表示されているすべての DLL ファイルを読み込もうとします。</span><span class="sxs-lookup"><span data-stu-id="87435-341">Beginning in PowerShell 6.2, PowerShell attempts to load all the DLL files listed in **FileList** property of the module manifest.</span></span> <span data-ttu-id="87435-342">ネイティブ Dll が **FileList** 内にある場合は、プロセスに読み込むことができず、エラーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="87435-342">Native DLLs is in the **FileList** fail to load in the process and the error is ignored.</span></span> <span data-ttu-id="87435-343">すべてのマネージ Dll がプロセスに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="87435-343">All managed DLLs are loaded in the process.</span></span> <span data-ttu-id="87435-344">この動作は、PowerShell 7.1 で削除されました。</span><span class="sxs-lookup"><span data-stu-id="87435-344">This behavior was removed in PowerShell 7.1.</span></span>

<span data-ttu-id="87435-345">PowerShell 2.0 では、 `New-ModuleManifest` モジュールマニフェストで要求されなかった場合でも、の多くのパラメーターが必須でした。</span><span class="sxs-lookup"><span data-stu-id="87435-345">In PowerShell 2.0, many parameters of `New-ModuleManifest` were mandatory, even though they weren't required in a module manifest.</span></span> <span data-ttu-id="87435-346">PowerShell 3.0 以降では、 **Path** パラメーターだけが必須です。</span><span class="sxs-lookup"><span data-stu-id="87435-346">Beginning in PowerShell 3.0, only the **Path** parameter is mandatory.</span></span>

<span data-ttu-id="87435-347">セッションは、PowerShell 実行環境のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="87435-347">A session is an instance of the PowerShell execution environment.</span></span> <span data-ttu-id="87435-348">セッションは、1 つまたは複数のセッション状態の場合があります。</span><span class="sxs-lookup"><span data-stu-id="87435-348">A session can have one or more session states.</span></span> <span data-ttu-id="87435-349">既定では、セッションはグローバルなセッション状態のみですが、インポートされた各モジュールは独自のセッション状態があります。</span><span class="sxs-lookup"><span data-stu-id="87435-349">By default, a session has only a global session state, but each imported module has its own session state.</span></span> <span data-ttu-id="87435-350">セッション状態によって、モジュール内のコマンドは、グローバルなセッション状態に影響を与えずに実行できます。</span><span class="sxs-lookup"><span data-stu-id="87435-350">Session states allow the commands in a module to run without affecting the global session state.</span></span>

<span data-ttu-id="87435-351">呼び出し元のセッション状態は、モジュールのインポート先のセッション状態です。</span><span class="sxs-lookup"><span data-stu-id="87435-351">The caller's session state is the session state into which a module is imported.</span></span> <span data-ttu-id="87435-352">通常は、グローバルなセッション状態を指しますが、モジュールが入れ子になったモジュールをインポートする場合、呼び出し元はモジュールであり、呼び出し元のセッション状態はモジュールのセッション状態です。</span><span class="sxs-lookup"><span data-stu-id="87435-352">Typically, it refers to the global session state, but when a module imports nested modules, the caller is the module and the caller's session state is the module's session state.</span></span>

## <span data-ttu-id="87435-353">関連リンク</span><span class="sxs-lookup"><span data-stu-id="87435-353">RELATED LINKS</span></span>

[<span data-ttu-id="87435-354">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="87435-354">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="87435-355">Get-Module</span><span class="sxs-lookup"><span data-stu-id="87435-355">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="87435-356">Import-Module</span><span class="sxs-lookup"><span data-stu-id="87435-356">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="87435-357">New-Module</span><span class="sxs-lookup"><span data-stu-id="87435-357">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="87435-358">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="87435-358">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="87435-359">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="87435-359">Test-ModuleManifest</span></span>](Test-ModuleManifest.md)

[<span data-ttu-id="87435-360">about_Modules</span><span class="sxs-lookup"><span data-stu-id="87435-360">about_Modules</span></span>](./About/about_Modules.md)
