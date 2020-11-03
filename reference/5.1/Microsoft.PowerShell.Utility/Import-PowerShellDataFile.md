---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: 61e3a7f941155ccf3db84a7e9ec8d2c48b4cceea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213859"
---
# Import-PowerShellDataFile

## 概要
内容を呼び出さずに、ファイルから値をインポート `.PSD1` します。

## SYNTAX

### ByPath (既定値)

```
Import-PowerShellDataFile [[-Path] <String[]>] [<CommonParameters>]
```

### ByLiteralPath

```
Import-PowerShellDataFile [-LiteralPath <String[]>] [<CommonParameters>]
```

## Description

`Import-PowerShellDataFile`コマンドレットは、ファイルで定義されているハッシュテーブルからキーと値のペアを安全にインポートし `.PSD1` ます。 値は、 `Invoke-Expression` ファイルの内容に対してを使用してインポートできます。
ただし、は、 `Invoke-Expression` ファイルに格納されているすべてのコードを実行します。 これは、望ましくない結果を生成したり、アンセーフコードを実行したりする可能性があります `Import-PowerShellDataFile` コードを呼び出さずにデータをインポートします。

## 例

### 例 1: .PSD1 から値を取得する

この例では、ハッシュテーブルに格納されているキーと値のペアを取得、ファイル内に保持し `Configuration.psd1` ます。 `Get-Content` は、ファイルの内容を表示するために使用され `Configuration.psd1` ます。

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## PARAMETERS

### -LiteralPath

インポートされるファイルへのパス。 パス内のすべての文字は、リテラル値として扱われます。
ワイルドカード文字は処理されません。

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

インポートされるファイルへのパス。 ワイルドカードは使用できますが、最初に一致するファイルのみがインポートされます。

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

## 出力

### System.Collections.Hashtable

## 注

## 関連リンク

[Invoke-Expression](Invoke-Expression.md)

[Import-LocalizedData](Import-LocalizedData.md)
