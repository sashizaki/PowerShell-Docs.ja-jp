---
title: ISESnippetCollection オブジェクト
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ae974955-4282-4cbc-8c42-0fff1904ef32
---
# ISESnippetCollection オブジェクト
  **ISESnippetCollection** オブジェクトは、**ISESnippet** オブジェクトのコレクションです。 **PowerShellTab** オブジェクトに関連付けられているファイル コレクションは、このクラスのメンバーです。 例としては、**$psISE.CurrentPowerShellTab.Files** コレクションです。

## メソッド

### Load\( FilePathName \)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 ユーザー定義のスニペットを含む .snippets.ps1xml ファイルを読み込みます。 スニペットを作成する最も簡単な方法は、New\-IseSnippet コマンドレットを使用することです。このコマンドレットでは、Windows PowerShell ISE を開始するたびにスニペットがロードされるように、自動的にスニペットをプロファイル フォルダーに保存します。

 **FilePathName** -文字列
 スニペット定義を含む .snippets.ps1xml ファイルへのパスとファイル名。

```
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) “Snippets\MySnips.snippets.ps1xml” $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)

```

## 参照
 [ISESnippetObject](The-ISESnippetObject.md) 
 [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
 [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
 [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)

  


<!--HONumber=May16_HO2-->


