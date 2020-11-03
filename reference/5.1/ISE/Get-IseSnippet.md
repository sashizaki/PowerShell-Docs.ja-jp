---
external help file: ISE-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218104"
---
# Get-IseSnippet

## 概要
ユーザーが作成したスニペットを取得します。

## SYNTAX

```
Get-IseSnippet [<CommonParameters>]
```

## Description

`Get-IseSnippet`コマンドレットは、ユーザーが作成した再利用可能なテキストスニペットを含む types.ps1xml ファイルを取得します。 Windows PowerShell Integrated Scripting Environment (ISE) でのみ動作します。

コマンドレットを使用してスニペットを作成すると `New-IseSnippet` 、に `New-IseSnippet` よっ `<SnippetTitle>.Snippets.ps1xml` てディレクトリにファイルが作成さ `$home\Documents\WindowsPowerShell\Snippets` れます。
`Get-IseSnippet` スニペットディレクトリ内のスニペットファイルを取得します。

このコマンドレットは、コマンドレットを使用してモジュールからインポートされる組み込みのスニペットやスニペットを取得しません `Import-IseSnippet` 。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: すべてのユーザー定義スニペットを取得する

この例では、スニペットディレクトリ内のすべてのユーザー定義スニペットを取得します。

```powershell
Get-IseSnippet
```

### 例 2: すべてのユーザー定義スニペットをリモートコンピューターから共有ディレクトリにコピーする

この例では、ユーザーが作成したすべてのスニペットを、リモートコンピューターのグループから共有スニペットディレクトリにコピーします。

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

`Invoke-Command``Get-IseSnippet`ファイル内のコンピューター上で実行さ `Servers.txt` れます。 パイプライン演算子 ( `|` ) によって、スニペットファイルが `Copy-Item` コマンドレットに送信され、 **Destination** パラメーターで指定されたディレクトリにコピーされます。

### 例 3: ローカルコンピューター上の各スニペットのタイトルとテキストを表示する

この例では `Get-IseSnippet` 、 `Select-Xml` コマンドレットとコマンドレットを使用して、ローカルコンピューター上の各スニペットのタイトルとテキストを表示します。

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### 例 4: セッション内のすべてのスニペットのタイトルと説明を表示する

この例では、組み込みのスニペット、ユーザー定義のスニペット、およびインポートされたスニペットを含む、セッション内のすべてのスニペットのタイトルと説明を表示します。

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

変数は、 `$PSISE` Windows PowerShell ISE ホストプログラムを表します。 変数の **Currentpowershelltab** プロパティは、 `$PSISE` 現在のセッションを表します。 **Snippets** プロパティは、現在のセッションのスニペットを表します。

コマンドは、コマンド `$PSISE.CurrentPowerShellTab.Snippets` レットとは異なり、スニペットを表す **new-isesnippet** オブジェクトを返します。 `Get-IseSnippet` `Get-IseSnippet` スニペットファイルを表すファイルオブジェクト (system.object) を返します。

コマンドレットでは、 `Format-Table` テーブル内のスニペットの **displaytitle** プロパティと **Description** プロパティを表示します。

## PARAMETERS

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

## 出力

### システム. IO. FileInfo

このコマンドレットは、スニペットファイルを表すファイルオブジェクトを返します。

## 注

* `New-IseSnippet`コマンドレットは、新しいユーザーが作成したスニペットを types.ps1xml ファイルに格納します。 そのため、Windows PowerShell は、実行ポリシーが **AllSigned** または **Restricted** のセッションにこれらを追加できません。 **Restricted** または **AllSigned** セッションでは、ユーザーが作成した署名されていないスニペットを作成、取得、およびインポートできますが、それらをセッションで使うことはできません。

  コマンドレットから返される、署名されていないユーザーが作成したスニペットを使用するには、 `Get-IseSnippet` 実行ポリシーを変更し、Windows PowerShell ISE を再起動します。

  Windows PowerShell 実行ポリシーの詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)」を参照してください。

## 関連リンク

[New-IseSnippet](New-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
