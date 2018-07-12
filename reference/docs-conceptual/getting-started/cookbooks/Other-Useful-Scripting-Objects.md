---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: その他の役に立つスクリプティング オブジェクト
ms.assetid: 4d781196-720b-4ccc-90d2-c570e5e719f5
ms.openlocfilehash: 2ae9bc1864daedbcb0070c5f3862a6c98f8db2d4
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893282"
---
# <a name="other-useful-scripting-objects"></a>その他の役に立つスクリプティング オブジェクト

次のオブジェクトは、Windows PowerShell ISE で追加のスクリプト機能を提供します。 これらのオブジェクトは **$psISE** 階層の一部ではありません。

## <a name="useful-scripting-objects"></a>役に立つスクリプティング オブジェクト

### <a name="psunsupportedconsoleapplications"></a>$psUnsupportedConsoleApplications

Windows PowerShell ISE がコンソール アプリケーションと対話操作する方法に関していくつかの制限があります。 ユーザーの介入を必要とするコマンドまたは自動化スクリプトは、Windows PowerShell コンソールで機能する場合と同様には機能しない可能性があります。 Windows PowerShell ISE のコマンド ウィンドウでこれらのコマンドまたはスクリプトが実行されないようにすることをお勧めします。 **$PsUnsupportedConsoleApplications** オブジェクトは、このようなコマンドの一覧を保持します。 この一覧に含まれるコマンドを実行しようとすると、そのコマンドがサポートされていないことを示すメッセージが表示されます。 次のスクリプトによって一覧にエントリが追加されます。

```powershell
# List the unsupported commands
$psUnsupportedConsoleApplications

# Add a command to this list
$psUnsupportedConsoleApplications.Add('Mycommand')

# Show the augmented list of commands
$psUnsupportedConsoleApplications
```

### <a name="pslocalhelp"></a>$psLocalHelp

これは、ヘルプ トピックと、ローカルのコンパイル済み HTML ヘルプ ファイル内の関連するリンクの間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。 特定のトピックのローカル ヘルプを見つけるために使用されます。 この一覧からトピックを追加または削除することができます。 次のコード例では、`$psLocalHelp` に含まれているキーと値のペアの例を示します。

```powershell
# See the local help map
$psLocalHelp | Format-List
```

### <a name="pslocalhelp-sample-output"></a>$psLocalHelp のサンプル出力

|||
|-|-|
|キー: Add-Computer|値: WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm|
|キー: Add-Content|値: WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm|

次のスクリプトによって一覧にエントリが追加されます。

```powershell
$psLocalHelp.Add("get-myNoun", "c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a>$psOnlineHelp

これは、ヘルプ トピックのトピック タイトルと、関連する外部 URL の間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。 Web で特定のトピックのヘルプを見つけるために使用されます。 この一覧からトピックを追加または削除することができます。

```powershell
$psOnlineHelp | Format-List
```

## <a name="psonilnehelp-sample-output"></a>$psOnilneHelp のサンプル出力

|||
|-|-|
|キー: Add-Computer|値: http://go.microsoft.com/fwlink/p/?LinkID=135194|
|キー: Add-Content|値: http://go.microsoft.com/fwlink/p/?LinkID=113278|

次のスクリプトによって一覧にエントリが追加されます。

```powershell
$psOnlineHelp.Add("get-myNoun", "http://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a>参照

[Windows PowerShell ISE スクリプト オブジェクト モデルの目的](../../core-powershell/ise/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)