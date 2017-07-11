---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Save-Script
ms.openlocfilehash: 7b692d33e3f86a89505b8d37c0da4177f3dff2c2
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="save-script" class="xliff"></a>

# Save-Script

Save-Script コマンドレットでは、指定した場所に保存することによって、スクリプト ファイルを確認できます。

<a id="description" class="xliff"></a>

## 説明

Save-Script コマンドレットは指定したスクリプトを保存します。

<a id="cmdlet-syntax" class="xliff"></a>

## コマンドレット構文

```powershell
Get-Command -Name Save-Script -Module PowerShellGet -Syntax
```
<a id="cmdlet-online-help-reference" class="xliff"></a>

## コマンドレット オンライン ヘルプ リファレンス

[Save-Script](http://go.microsoft.com/fwlink/?LinkId=619786)

<a id="example-commands" class="xliff"></a>

## コマンド例

<a id="example-1-save-a-script-from-a-repository" class="xliff"></a>

### 例 1: リポジトリからスクリプトを保存する
このコマンドは、最新バージョンのスクリプト Fabrikam-ClientScript を GalleryINT リポジトリからローカル フォルダー C:\ScriptSharingDemo に保存します

```powershell
Save-Script -Name Fabrikam-ClientScript -Repository GalleryINT -Path C:\ScriptSharingDemo
```

<a id="example-2-save-a-version-of-a-script-by-piping-from-the-find-script-cmdlet" class="xliff"></a>

### 例 2: Find-Script コマンドレットからパイプして、スクリプトのバージョンを保存する

最初のコマンドで、リポジトリ GalleryINT からバージョン 1.5 の Fabrikam-ClientScript を検索して、フォルダー C:\ScriptSharingDemo に保存します

2 番目のコマンドで、保存したスクリプト メタデータを検証します。

```powershell
Find-Script -Name Fabrikam-ClientScript -Repository GalleryINT -RequiredVersion 1.5 | Save-Script -Path C:\\ScriptSharingDemo
Test-ScriptFileInfo C:\\ScriptSharingDemo\\Fabrikam-ClientScript.ps1

Version Name Author Description
------- ---- ------ -----------
1.5 Fabrikam-ClientScript manikb Description for the Fabrikam-ClientScript script
```

