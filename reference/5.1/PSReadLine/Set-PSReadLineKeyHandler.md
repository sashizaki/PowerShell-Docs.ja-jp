---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadline
ms.date: 02/16/2021
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 220b38f51afab619a57473be27b1139b878eb7e9
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563228"
---
# Set-PSReadLineKeyHandler

## 概要
ユーザー定義キーまたは PSReadLine キーハンドラー関数にキーをバインドします。

## SYNTAX

### スクリプト ブロック

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### 機能

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## Description

`Set-PSReadLineKeyHandler`キーまたはキーのシーケンスが押されたときに、コマンドレットによって結果がカスタマイズされます。 ユーザー定義のキーバインドを使用すると、PowerShell スクリプト内から可能なほとんどすべての操作を実行できます。

## 例

### 例 1: 関数に方向キーをバインドする

このコマンドは、↑キーを **History Search後方** 関数にバインドします。 この関数は、コマンドラインの現在の内容で始まるコマンドラインを検索します。

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### 例 2: キーをスクリプトブロックにバインドする

この例では、1つのキーを使用してコマンドを実行する方法を示します。 このコマンドは、 `Ctrl+B` 行をクリアするスクリプトブロックにキーをバインドし、"build" という単語を挿入して、その行を受け入れます。

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## PARAMETERS

### -BriefDescription

キーバインドの簡単な説明。 この説明はコマンドレットによって表示され `Get-PSReadLineKeyHandler` ます。

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -コード

関数またはスクリプトブロックにバインドするキーまたはキーのシーケンス。 単一の文字列を使用して1つのバインドを指定します。 バインドが一連のキーである場合は、次の例のように、キーをコンマで区切ります。

`Ctrl+X,Ctrl+L`

> [!NOTE]
> PSReadLine 2.0.0 の場合、 **コード** パラメーターでは **大文字と小文字が区別** されます。 つまり、 `Ctrl+X` と `Ctrl+x` は異なるバインドを作成します。

このパラメーターは、文字列の配列を受け入れます。 各文字列は個別のバインドであり、1つのバインドのキーのシーケンスではありません。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

コマンドレットの出力に表示されるキーバインドの詳細な説明を指定し `Get-PSReadLineKeyHandler` ます。

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases: LongDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -関数

PSReadLine によって提供される既存のキーハンドラーの名前を指定します。 このパラメーターを使用すると、既存のキーバインドを再バインドしたり、現在バインドされていないハンドラーをバインドしたりできます。

```yaml
Type: System.String
Parameter Sets: Function
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

コードの入力時に実行するスクリプトブロックの値を指定します。 PSReadLine は、このスクリプトブロックに1つまたは2つのパラメーターを渡します。 最初のパラメーターは、押されたキーを表す **Consolekeyinfo** オブジェクトです。 2番目の引数には、コンテキストに応じて任意のオブジェクトを指定できます。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ViMode

バインドが適用される vi モードを指定します。

次の値を指定できます。

- 挿入
- コマンド

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

## 関連リンク

[Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)

[-PSReadLineKeyHandler を削除します。](Remove-PSReadLineKeyHandler.md)

[Get-PSReadLineOption](Get-PSReadLineOption.md)

[設定-PSReadLineOption](Set-PSReadLineOption.md)
