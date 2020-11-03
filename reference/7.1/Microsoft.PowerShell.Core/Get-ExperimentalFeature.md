---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: 2d91c36c6fd6d2e1281fdadf95c3b83e27c36f60
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217723"
---
# Get-ExperimentalFeature

## 概要
試験的な機能を取得します。

## SYNTAX

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## Description

`Get-ExperimentalFeature`コマンドレットは、PowerShell によって検出されたすべての試験的な機能を返します。
試験的な機能は、モジュールまたは PowerShell エンジンから取得できます。 試験的な機能を使用すると、ユーザーは新しい機能を安全にテストし、(通常は GitHub 経由で) フィードバックを提供する前に、設計が完了したと見なされ、変更が重大な変更になる可能性があります。

## 例

### 例 1

現在登録されている試験的な機能とその現在の状態の一覧を取得します。

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## PARAMETERS

### -Name

返される特定の実験的な機能の名前または名前。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.String[]

返される試験的な機能の名前または名前。

## 出力

### ExperimentalFeature

名前が指定されていない場合は、要求された名前またはすべての試験的な機能に一致するインスタンスを返します。

## 関連リンク

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)

