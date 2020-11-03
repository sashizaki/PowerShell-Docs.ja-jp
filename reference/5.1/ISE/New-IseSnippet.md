---
external help file: ISE-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212379"
---
# New-IseSnippet

## 概要
Windows PowerShell ISE のコード スニペットを作成します。

## SYNTAX

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## Description

コマンドレットにより、 `New-ISESnippet` Windows PowerShell ISE 用の再利用可能なテキスト "スニペット" が作成されます。 スニペットを使用すると、Windows PowerShell ISE のスクリプト ペインまたはコマンド ペインにテキストを追加できます。 このコマンドレットは、Windows PowerShell ISE でのみ使用できます。

Windows PowerShell 3.0 以降、Windows PowerShell ISE には組み込みのスニペットのコレクションが含まれます。 `New-ISESnippet`コマンドレットを使用すると、独自のスニペットを作成して組み込みコレクションに追加できます。 スニペット ファイルは、表示、変更、追加、削除、および共有でき、Windows PowerShell モジュールに含めることができます。 Windows PowerShell ISE のスニペットを表示するには、[ **編集** ] メニューの [ **スニペットの開始** ] を選択するか、 <kbd>CTRL</kbd> + <kbd>J</kbd>キーを押します。

`New-ISESnippet`コマンドレットにより、指定した `<Title>.Snippets.ps1xml` タイトルのファイルがディレクトリに作成され `$home\Documents\WindowsPowerShell\Snippets` ます。 作成しているモジュールにスニペット ファイルを含めるには、モジュール ディレクトリの Snippets サブディレクトリにスニペット ファイルを追加します。

実行ポリシーが **Restricted** または **AllSigned** のセッションでは、ユーザーが作成したスニペットを使用できません。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: Comment-Based ヘルプスニペットを作成する

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

このコマンドは、Windows PowerShell ISE の Comment-BasedHelp スニペットを作成します。 これにより、という名前のファイルが `Comment-BasedHelp.snippets.ps1xml` ユーザーのスニペットディレクトリに作成さ `$home\Documents\WindowsPowerShell\Snippets` れます。

### 例 2: 必須のスニペットを作成する

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

この例では、Windows PowerShell ISE に **必須** という名前のスニペットを作成します。 最初のコマンドは、変数にスニペットのテキストを保存し `$M` ます。 2番目のコマンドは、 `New-ISESnippet` コマンドレットを使用してスニペットを作成します。 このコマンドは、 **Force** パラメーターを使用して、同じ名前で前のスニペットを上書きします。

### 例 3: 必須のスニペットをフォルダーから目的のフォルダーにコピーする

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

このコマンドは、コマンドレットを使用して、 `Copy-Item` がファイル共有に置かれているフォルダーから **必須** のスニペットをコピーし `New-ISESnippet` ます。

## PARAMETERS

### -作成者

スニペットの作成者を指定します。 作成者フィールドは、スニペット ファイルに表示されますが、Windows PowerShell ISE でスニペットの名前をクリックしたときに表示されません。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CaretOffset

このコマンドレットがカーソルを配置するスニペットテキストの文字を指定します。 カーソルの位置を表す整数を入力します。"1" は、テキストの最初の文字を表します。 既定値の 0 (ゼロ) の場合、テキストの最初の文字の直前にカーソルが配置されます。 このパラメーターは、スニペットのテキストをインデントする機能は提供しません。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

スニペットの説明を指定します。 説明の値は、Windows PowerShell ISE でスニペット名をクリックしたときに表示されます。 このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

このコマンドレットが同じ場所にある同じ名前のスニペットファイルを上書きすることを示します。 既定で `New-ISESnippet` は、はファイルを上書きしません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Text

スニペットを選択するときに追加されるテキスト値を指定します。 スニペットのテキストは、Windows PowerShell ISE でスニペット名をクリックしたときに表示されます。 このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

スニペットのタイトルまたは名前を指定します。 このタイトルはスニペット ファイルの名前にも使用されます。 このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

このコマンドレットはパイプラインから入力を取得しません。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

`New-IseSnippet` 新しいユーザーが作成したスニペットを types.ps1xml ファイルに格納します。 そのため、Windows PowerShell は、実行ポリシーが **AllSigned** または **Restricted** のセッションにこれらを追加できません。 **Restricted** または **AllSigned** セッションでは、ユーザーが作成した署名されていないスニペットを作成、取得、およびインポートできますが、それらをセッションで使うことはできません。

`New-IseSnippet`**制限付き** セッションまたは **AllSigned** セッションでコマンドレットを使用すると、スニペットが作成されますが、Windows PowerShell が新しく作成されたスニペットをセッションに追加しようとすると、エラーメッセージが表示されます。 新しいスニペット (およびその他のユーザーが作成した署名されていないスニペット) を使用するには、実行ポリシーを変更してから Windows PowerShell ISE を再起動します。

Windows PowerShell 実行ポリシーの詳細については、「about_Execution_Policies」を参照してください。

- スニペットを変更するには、スニペットファイルを編集します。 スニペットファイルは Windows PowerShell ISE のスクリプトウィンドウで編集できます。
- 追加したスニペットを削除するには、スニペットファイルを削除します。
- 組み込みのスニペットを削除することはできませんが、"$psise を使用すると、組み込みのスニペットをすべて非表示にすることができます。Options. ShowDefaultSnippets = $false "コマンド。
- 組み込みのスニペットと同じ名前を持つスニペットを作成できます。 両方のスニペットが、Windows PowerShell ISE のスニペット メニューに表示されます。

## 関連リンク

[Get-IseSnippet](Get-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
