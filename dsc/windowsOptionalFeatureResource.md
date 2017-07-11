---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC WindowsOptionalFeature リソース"
ms.openlocfilehash: 388fbe1bc430098d6680902e0b5643243fbf7f4c
ms.sourcegitcommit: 79e8f03afb8d0b0bb0a167e56464929b27f51990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2017
---
<a id="dsc-windowsoptionalfeature-resource" class="xliff"></a>

# DSC WindowsOptionalFeature リソース

> 適用先: Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) の **WindowsOptionalFeature** リソースは、オプション機能をターゲット ノードで有効にするためのメカニズムを備えています。

<a id="syntax" class="xliff"></a>

## 構文

```
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Enable | Disable }  ]
    [ Source = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    
}
```

<a id="properties" class="xliff"></a>

## プロパティ

|  プロパティ  |  説明   | 
|---|---| 
| 名前| 有効または無効にする機能の名前を示します。| 
| Ensure| 機能が有効化かどうかを指定します。 機能を確実に有効にするには、このプロパティを "Enable" に設定します。機能を確実に無効にするには、このプロパティを "Disable" に設定します。|
| ソース| 実装されていません。|
| NoWindowsUpdateCheck| 機能を有効にするソース ファイルを検索するとき、DISM が Windows Update (WU) を確認するかどうかを指定します。 $true の場合、DISM は WU を確認しません。|
| RemoveFilesOnDisable| **[$true]** に設定すると、無効時に (つまり、**[Ensure]** が "Absent" に設定されているとき)、機能に関連付けられているすべてのファイルが削除されます。|
| ログ レベル| ログに表示される最大の出力レベル。 有効な値は "ErrorsOnly" (エラーのみが記録されます)、"ErrorsAndWarning" (エラーと警告が記録されます)、"ErrorsAndWarningAndInformation" (エラー、警告、デバッグ情報が記録されます) です。|
| LogPath| リソース プロバイダーの操作を記録するログ ファイルへのパス。| 
| DependsOn| このリソースを構成する前に、他のリソースの構成を実行する必要があることを指定します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。| 
 



