---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: scriptwithpseditionsupport
ms.openlocfilehash: e6994b994cb15903560f3dd89c21383fb2cd367d
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="script-with-compatible-powershell-editions" class="xliff"></a>

# 互換性のある PowerShell エディションが含まれるスクリプト
バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。

- **デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。
- **コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。

PowerShell の実行中のエディションが $PSVersionTable の PSEdition プロパティに表示されます。
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

スクリプト作成者は、#requires ステートメント上で #requires パラメーターを使用すれば、PowerShell の互換性のあるエディションで実行されていない限り、スクリプトの実行を回避できます。
```powershell
Set-Content C:\script.ps1 -Value "#requires -PSEdition Core
Get-Process -Name PowerShell"
Get-Content C:\script.ps1
#requires -PSEdition Core
Get-Process -Name PowerShell

C:\script.ps1
C:\script.ps1 : The script 'script.ps1' cannot be run because it contained a "#requires" statement for PowerShell Core edition. The edition of PowerShell that is required by the script does not match the currently running PowerShell Desktop edition.
At line:1 char:1
+ C:\script.ps1
+ ~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (script.ps1:String) [], RuntimeException
    + FullyQualifiedErrorId : ScriptRequiresUnmatchedPSEdition
```

PowerShell Gallery ユーザーは、PowerShell の特定のエディションでサポートされているスクリプトの一覧を検索できます。
PSEdition_Desktop および PSEditon_Core のないスクリプトは、PowerShell Desktop エディションで正常に動作すると見なされます。

```powershell

# Find scripts supported on PowerShell Desktop edition
Find-Script -Tag PSEditon_Desktop

# Find scripts supported on PowerShell Core editions
Find-Script -Tag PSEditon_Core

```

<a id="more-details" class="xliff"></a>

## 詳細情報
<a id="modules-with-pseditionsmodulemodulewithpseditionsupportmd" class="xliff"></a>

### [PSEditions が含まれるモジュール](../module/modulewithpseditionsupport.md)
<a id="pseditions-support-on-powershellgallerypsgallerypsgallerypseditionsmd" class="xliff"></a>

### [PowerShellGallery での PSEditions のサポート](../../psgallery/psgallery_pseditions.md)

