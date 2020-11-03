---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: f3230c247296d5fd907d580e719cbbbc560183a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214467"
---
# Set-Clipboard

## 概要
現在の Windows クリップボードエントリを設定します。

## SYNTAX

### String (既定値)

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 値

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Path

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

`Set-Clipboard`コマンドレットは、現在の Windows クリップボードエントリを設定します。

## 例

### 例 1: テキストをクリップボードにコピーする

```powershell
Set-Clipboard -Value "This is a test string"
```

### 例 2: ディレクトリの内容をクリップボードにコピーする

このコマンドは、指定されたフォルダーの内容をクリップボードにコピーします。

```powershell
Set-Clipboard -Path "C:\Staging\"
```

## PARAMETERS

### -追加

コマンドレットがクリップボードをクリアせずにコンテンツを追加しないことを示します。

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

### -AsHtml

コマンドレットによってコンテンツが HTML としてクリップボードに表示されることを示します。

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

### -LiteralPath

クリップボードにコピーされる項目へのパスを指定します。 **Path** とは異なり、 **LiteralPath** の値は入力した内容のまま使用されます。 ワイルドカードとして解釈される文字はありません。 パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。 単一引用符で囲んだ文字はエスケープ シーケンスとして解釈されません。

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

クリップボードにコピーされる項目へのパスを指定します。 ワイルドカード文字を使用できます。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Value

クリップボードにコピーするコンテンツを文字列配列として指定します。

```yaml
Type: System.String[]
Parameter Sets: Value
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

コマンドレットの実行前に確認を求めるメッセージが表示されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

コマンドレットの実行時に発生する内容を示します。 このコマンドレットは実行されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.String[]

## 出力

## 注

ループのように、頻繁に多数の値を指定してを使用する場合、 `Set-Clipboard` クリップボードから空白の値が返されることがまれにあります。 これは、ループ内でを使用して修正でき `Start-Sleep -Milliseconds 1` ます。

## 関連リンク

[Get-Clipboard](Get-Clipboard.md)
