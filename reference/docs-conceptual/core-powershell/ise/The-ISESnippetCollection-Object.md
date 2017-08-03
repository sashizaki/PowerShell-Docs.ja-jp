---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISESnippetCollection オブジェクト"
ms.assetid: ae974955-4282-4cbc-8c42-0fff1904ef32
ms.openlocfilehash: b19c5b5c88f7c8bd0d0c466c7861fa9288bdc7a2
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-isesnippetcollection-object"></a>ISESnippetCollection オブジェクト
  **ISESnippetCollection** オブジェクトは、**ISESnippet** オブジェクトのコレクションです。 **PowerShellTab** オブジェクトに関連付けられているファイル コレクションは、このクラスのメンバーです。 例としては、**$psISE.CurrentPowerShellTab.Files** コレクションです。

## <a name="methods"></a>メソッド

### <a name="load-filepathname-"></a>Load\( FilePathName \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 ユーザー定義のスニペットを含む .snippets.ps1xml ファイルを読み込みます。 スニペットを作成する最も簡単な方法は、New-IseSnippet コマンドレットを使用することです。このコマンドレットでは、Windows PowerShell ISE を開始するたびにスニペットがロードされるように、自動的にスニペットをプロファイル フォルダーに保存します。

 **FilePathName** - スニペット定義を含む .snippets.ps1xml ファイルへのパスとファイル名。

```
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) “Snippets\MySnips.snippets.ps1xml” $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)

```

## <a name="see-also"></a>参照
- [ISESnippetObject](The-ISESnippetObject.md) 
- [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)

  
