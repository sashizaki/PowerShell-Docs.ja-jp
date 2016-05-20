---
title: その他の役に立つスクリプティング オブジェクト
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4d781196-720b-4ccc-90d2-c570e5e719f5
---
# その他の役に立つスクリプティング オブジェクト
  次のオブジェクトは、Windows PowerShell ISE で追加のスクリプト機能を提供します。 これらのオブジェクトは **$psISE** 階層の一部ではありません。

## 役に立つスクリプティング オブジェクト

### $psUnsupportedConsoleApplications
 Windows PowerShell ISE がコンソール アプリケーションと対話操作する方法に関していくつかの制限があります。 ユーザーの介入を必要とするコマンドまたは自動化スクリプトは、Windows PowerShell コンソールで機能する場合と同様には機能しない可能性があります。 Windows PowerShell ISE のコマンド ウィンドウでこれらのコマンドまたはスクリプトが実行されないようにすることをお勧めします。 **$PsUnsupportedConsoleApplications** オブジェクトは、このようなコマンドの一覧を保持します。 この一覧に含まれるコマンドを実行しようとすると、そのコマンドがサポートされていないことを示すメッセージが表示されます。 次のスクリプトによって一覧にエントリが追加されます。

```
# List the unsupported commands
psUnsupportedConsoleApplications
# Add a command to this list
psUnsupportedConsoleApplications.Add(“Mycommand”)
#Show the augmented list of commands
psUnsupportedConsoleApplications

```

### $psLocalHelp
 これは、ヘルプ トピックと、ローカルのコンパイル済み HTML ヘルプ ファイル内の関連するリンクの間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。 特定のトピックのローカル ヘルプを見つけるために使用されます。 この一覧からトピックを追加または削除することができます。 次のコード例では、**$psLocalHelp** に含まれているキーと値のペアの例を示します。.

```
# See the local help map
$psLocalHelp |Format-List

```

### サンプル出力

|||
|-|-|
|キー: Add-Computer|値: WindowsPowerShellHelp.chm::\/html\/093f660c\-b8d5\-43cf\-aa0c\-54e5e54e76f9.htm|
|キー: Add-Content|値: WindowsPowerShellHelp.chm::\/html\/0c836a1b\-f389\-4e9a\-9325\-0f415686d194.htm|

 次のスクリプトによって一覧にエントリが追加されます。

```
$psLocalHelp.Add("get-myNoun","c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### $psOnlineHelp
 これは、ヘルプ トピックのトピック タイトルと、関連する外部 URL の間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。 Web で特定のトピックのヘルプを見つけるために使用されます。 この一覧からトピックを追加または削除することができます。

```
$psOnlineHelp |format-list

```

### サンプル出力

|||
|-|-|
|キー: Add-Computer|値: http:\/\/go.microsoft.com\/fwlink\/p\/?LinkID\=135194|
|キー: Add-Content|値: http:\/\/go.microsoft.com\/fwlink\/p\/?LinkID\=113278|

 次のスクリプトによって一覧にエントリが追加されます。

```
$psOnlineHelp.Add("get-myNoun","http://www.mydomain.com/MyNoun.html")
```

## 参照
 [Windows PowerShell ISE スクリプト オブジェクト モデル](../../core-powershell/ise/The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  


<!--HONumber=May16_HO2-->


