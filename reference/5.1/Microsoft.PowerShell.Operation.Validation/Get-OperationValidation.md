---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214288"
---
# Get-OperationValidation

## 概要
操作検証フレームワークテストを取得します。

## SYNTAX

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## Description
**Get operationvalidation** コマンドレットは、インストールされているモジュールの操作検証フレームワークテストを取得します。

診断フォルダーを含むモジュールは、Simple または包括的なサブフォルダー、またはその両方で、Pester テストが検査されます。

## 例

### 例 1: 操作検証テストを取得する

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

このコマンドは、C:\temp\modules フォルダー内の AddNumbers という名前のモジュールから検証テストを取得します。

## PARAMETERS

### -ModuleName
モジュールの名前の配列を指定します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestType
テストの種類の配列を指定します。
有効な値は、Simple、包括的、または both です。
既定値は "Simple, 包括的" です。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

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
このコマンドレットに入力をパイプすることはできません。

## 出力

### PSCustomObject
**Pscustomobject** 検証について説明します。

## 注

## 関連リンク

[Invoke-OperationValidation](Invoke-OperationValidation.md)
