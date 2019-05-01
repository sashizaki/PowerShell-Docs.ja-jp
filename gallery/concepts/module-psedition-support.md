---
ms.date: 03/28/2019
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: 互換性のある PowerShell エディションが含まれるモジュール
ms.openlocfilehash: 425588c168a4f864fdc0c52aa53cfd748b80dc98
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084727"
---
# <a name="modules-with-compatible-powershell-editions"></a>互換性のある PowerShell エディションが含まれるモジュール

バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。

- **Desktop Edition:**.NET Framework に基づいて構成され、Windows デスクトップ、Windows Server、Windows Server Core、およびその他のほとんどの Windows エディション上の Windows PowerShell v4.0 以下と Windows PowerShell 5.1 に適用されます。
- **Core Edition:**.NET Core に基づいて構築され、Windows IoT や Windows Nanoserver などのフットプリントが小さい Windows エディション上の PowerShell Core 6.0 以上と Windows PowerShell 5.1 に適用されます。

PowerShell のエディションの詳細については、[about_PowerShell_Editions][] に関するページをご覧ください。

## <a name="declaring-compatible-editions"></a>互換性のあるエディションを宣言する

モジュールの作成者は、CompatiblePSEditions モジュール マニフェスト キーを使用して、モジュールが 1 つ以上の PowerShell エディションと互換性があることを宣言できます。 このキーは、PowerShell 5.1 以降でのみサポートされます。

> [!NOTE]
> CompatiblePSEditions キーを使用してモジュール マニフェストを指定すると、バージョン 4 以下の PowerShell にはインポートできません。

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

使用可能なモジュールの一覧を取得するときには、PowerShell のエディションを条件としてフィルター処理できます。

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

## <a name="targeting-multiple-editions"></a>複数のエディションを対象にする

モジュールの作成者が、PowerShell エディションのどちらかまたは両方を対象とする 1 つのモジュールを発行することができます。

1 つのモジュールが、デスクトップとコアの両方のエディションで動作します。そのモジュール内で、作成者は、$PSEdition 変数を使用して、RootModule またはモジュール マニフェストで必要なロジックを追加する必要があります。 モジュールでは、CoreCLR と FullCLR の両方を対象とするコンパイル済み DLL の 2 つのセットを使用できます。 次に、適切な dll を読み込むためのロジックを含むモジュールをパッケージ化するためのいくつかのオプションを示します。

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a>オプション 1: PowerShell の複数のバージョンおよび複数のエディションをターゲットとしてモジュールをパッケージ化する

モジュール フォルダーの内容

- Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- PSScriptAnalyzer.psd1
- PSScriptAnalyzer.psm1
- ScriptAnalyzer.format.ps1xml
- ScriptAnalyzer.types.ps1xml
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- en-US\about_PSScriptAnalyzer.help.txt
- en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- Settings\CmdletDesign.psd1
- Settings\DSC.psd1
- Settings\ScriptFunctions.psd1
- Settings\ScriptingStyle.psd1
- Settings\ScriptSecurity.psd1

PSScriptAnalyzer.psd1 ファイルの内容

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

以下のロジックは、現在のエディションまたはバージョンに応じて必要なアセンブリを読み込みます。

PSScriptAnalyzer.psm1 ファイルの内容:

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

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls-and-nestedrequired-modules"></a>オプション 2:PSD1 ファイルで $PSEdition 変数を使用して適切な DLL と入れ子になった/必要なモジュールを読み込む

PS 5.1 以降では、$PSEdition グローバル変数をモジュール マニフェスト ファイル内で使用できます。 この変数を使用すると、モジュールの作成者が、モジュール マニフェスト ファイル内で条件値を指定できます。 $PSEdition 変数は、制限された言語モードまたはデータ セクション内で参照できます。

> [!NOTE]
> CompatiblePSEditions キーまたは `$PSEdition` 変数を使用してモジュール マニフェストを指定した後、古いバージョンの PowerShell にインポートすることはできません。

CompatiblePSEditions キーを使用するサンプルのモジュール マニフェスト ファイル

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

### <a name="module-contents"></a>モジュールの内容

```powershell
dir -Recurse
```

```Output
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions

Mode           LastWriteTime   Length Name
----           -------------   ------ ----
d-----    7/5/2016   1:37 PM          clr
d-----    7/5/2016   1:36 PM          coreclr
-a----    7/5/2016   1:34 PM     4906 ModuleWithEditions.psd1

    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\clr

Mode           LastWriteTime    Length Name
----           -------------    ------ ----
-a----    7/5/2016   1:35 PM         0 MyFullClrNM1.dll
-a----    7/5/2016   1:35 PM         0 MyFullClrNM2.dll
-a----    7/5/2016   1:35 PM         0 MyFullClrRM.dl

    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\coreclr

Mode           LastWriteTime   Length Name
----           -------------   ------ ----
-a----    7/5/2016   1:35 PM        0 MyCoreClrNM1.dll
-a----    7/5/2016   1:35 PM        0 MyCoreClrNM2.dll
-a----    7/5/2016   1:35 PM        0 MyCoreClrRM.dl
```

PowerShell ギャラリー ユーザーは、PSEdition_Desktop および PSEdition_Core タグを使用して特定の PowerShell エディションでサポートされているモジュールの一覧を表示できます。

PSEdition_Desktop および PSEdition_Core タグがないモジュールは、PowerShell Desktop エディションで正常に動作するものと見なされます。

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="more-details"></a>詳細情報

[PSEditions のスクリプト](script-psedition-support.md)

[PowerShellGallery での PSEditions のサポート](../how-to/finding-packages/searching-by-compatibility.md)

[モジュール マニフェストを更新する](/powershell/module/powershellget/update-modulemanifest)

[about_PowerShell_Editions][]

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
