---
ms.date: 10/17/2017
contributor: keithb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Save-Script
ms.openlocfilehash: 67697fc0e70fb31cad9ad5ae7ce01debef160b81
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="save-script"></a>Save-Script

Save-Script コマンドレットでは、指定した場所に保存することによって、スクリプト ファイルを確認できます。

## <a name="description"></a>説明

Save-Script コマンドレットは指定したスクリプトを保存します。

## <a name="cmdlet-syntax"></a>コマンドレット構文

```powershell
Get-Command -Name Save-Script -Module PowerShellGet -Syntax
```
## <a name="cmdlet-online-help-reference"></a>コマンドレット オンライン ヘルプ リファレンス

[Save-Script](http://go.microsoft.com/fwlink/?LinkId=619786)

## <a name="example-commands"></a>コマンド例

### <a name="example-1-save-a-script-from-a-repository"></a>例 1: リポジトリからスクリプトを保存する
このコマンドは、最新バージョンのスクリプト Fabrikam-ClientScript を GalleryINT リポジトリからローカル フォルダー C:\ScriptSharingDemo に保存します

```powershell
Save-Script -Name Fabrikam-ClientScript -Repository GalleryINT -Path C:\ScriptSharingDemo
```

### <a name="example-2-save-a-version-of-a-script-by-piping-from-the-find-script-cmdlet"></a>例 2: Find-Script コマンドレットからパイプして、スクリプトのバージョンを保存する

最初のコマンドで、リポジトリ GalleryINT からバージョン 1.5 の Fabrikam-ClientScript を検索して、フォルダー C:\ScriptSharingDemo に保存します

2 番目のコマンドで、保存したスクリプト メタデータを検証します。

```powershell
Find-Script -Name Fabrikam-ClientScript -Repository GalleryINT -RequiredVersion 1.5 | Save-Script -Path C:\\ScriptSharingDemo
Test-ScriptFileInfo C:\\ScriptSharingDemo\\Fabrikam-ClientScript.ps1

Version Name Author Description
------- ---- ------ -----------
1.5 Fabrikam-ClientScript manikb Description for the Fabrikam-ClientScript script
```

### <a name="example-3-save-a-prerelease-version-of-a-script-from-a-repository"></a>例 3: リポジトリからプレリリース バージョンのスクリプトを保存する
このコマンドは、最新バージョンのスクリプト Fabrikam-ClientScript を GalleryINT リポジトリからローカル フォルダー C:\ScriptSharingDemo に保存します

```powershell
Save-Script -Name Fabrikam-ClientScript -Path C:\ScriptSharingDemo -AllowPrerelease
```