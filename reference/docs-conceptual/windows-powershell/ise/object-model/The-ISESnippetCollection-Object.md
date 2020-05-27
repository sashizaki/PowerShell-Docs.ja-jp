---
ms.date: 12/31/2019
keywords: powershell,コマンドレット
title: ISESnippetCollection オブジェクト
ms.openlocfilehash: 6cdc43dd1d82e94f66122d7f7b313c02e755fed7
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808578"
---
# <a name="the-isesnippetcollection-object"></a>ISESnippetCollection オブジェクト

**ISESnippetCollection** オブジェクトは、**ISESnippet** オブジェクトのコレクションです。 **PowerShellTab** オブジェクトに関連付けられているファイル コレクションは、このクラスのメンバーです。 例は、`$psISE.CurrentPowerShellTab.Files` コレクションです。

## <a name="methods"></a>メソッド

### <a name="load-filepathname-"></a>Load\( FilePathName \)

Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。

ユーザー定義のスニペットが含まれる `.snippets.ps1xml` ファイルを読み込みます。 スニペットを作成する最も簡単な方法は、`New-IseSnippet` コマンドレットを使用することです。このコマンドレットを使うと、Windows PowerShell ISE を開始するたびにスニペットがロードされるように、スニペットがプロファイル フォルダーに自動的に保存されます。

**FilePathName** - スニペット定義を含む .snippets.ps1xml ファイルへのパスとファイル名。

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a>参照

- [ISESnippetObject](The-ISESnippetObject.md)
- [Windows PowerShell ISE スクリプト オブジェクト モデルの目的](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)
