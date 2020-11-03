---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: f39add03a3b0250172cbb117a4233bb01958d9d3
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217952"
---
# Get-MarkdownOption

## 概要
コンソールで Markdown コンテンツをレンダリングするために使用される、現在の色とスタイルを返します。

## SYNTAX

```
Get-MarkdownOption [<CommonParameters>]
```

## Description

コンソールで Markdown コンテンツをレンダリングするために使用される、現在の色とスタイルを返します。 このコマンドレットの出力に表示される文字列には、表示される Markdown テキストの色とスタイルを変更するために使用する ANSI エスケープコードが含まれています。

Markdown の詳細については、「 [Commonmark](https://commonmark.org/) 」 web サイトを参照してください。

## 例

### 例 1-現在の色とスタイルを取得する

```powershell
Get-MarkdownOption
```

```Output
Header1         : [7m
Header2         : [4;93m
Header3         : [4;94m
Header4         : [4;95m
Header5         : [4;96m
Header6         : [4;97m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

> [!NOTE]
> 出力に表示される文字列値は、 **Escape** `[char]0x1B` ANSI エスケープシーケンスのエスケープ文字 () に続く文字です。 ANSI エスケープコードの詳細については、「 [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)」を参照してください。

## PARAMETERS

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

## 出力

### PSMarkdownOptionInfo を表示します。

## 注

## 関連リンク

[Set-MarkdownOption](Set-MarkdownOption.md)

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

[Show-Markdown](Show-Markdown.md)

[ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)

[CommonMark](https://commonmark.org/)
