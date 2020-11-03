---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "93220032"
---
# Get-Clipboard

## 概要
現在の Windows クリップボードエントリを取得します。

## SYNTAX

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## Description

`Get-Clipboard`コマンドレットは、現在の Windows クリップボードエントリを取得します。 に類似した文字列の配列として、複数行のテキストが返され `Get-Content` ます。

## 例

### 例 1: クリップボードの内容を取得し、それをコマンドラインに表示する

この例では、ブラウザーで画像を右クリックし、[ **コピー** ] アクションを選択しました。 次のコマンドは、クリップボードに格納されているイメージの URL としてのリンクを表示します。

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### 例 2: 特定の形式でクリップボードの内容を取得する

この例では、Windows Explorerby でファイルを選択し、 <kbd>Ctrl + C</kbd>キーを押して、ファイルをクリップボードにコピーしました。 次のコマンドを使用して、ファイルの一覧としてクリップボードの内容にアクセスできます。

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## PARAMETERS

### -形式

クリップボードの種類 (形式) を指定します。 このパラメーターの有効値は、次のとおりです。

- Text
- FileDropList
- Image
- オーディオ

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Raw

クリップボードの内容全体を取得します。 複数行テキストは、文字列の配列ではなく、単一の複数行文字列として返されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TextFormatType

クリップボードのテキストデータ形式の種類を指定します。 このパラメーターの有効値は、次のとおりです。

- Text
- UnicodeText
- Rtf
- Html
- CommaSeparatedValue

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

## 出力

### System.string, system.object, system.object, system.object, システムのイメージを作成します。

## 注

## 関連リンク

[Set-Clipboard](Set-Clipboard.md)
