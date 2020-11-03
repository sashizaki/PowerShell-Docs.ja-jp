---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215608"
---
# Checkpoint-Computer

## 概要
ローカル コンピューターのシステム復元ポイントを作成します。

## SYNTAX

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## Description

コマンドレットにより、 `Checkpoint-Computer` システムの復元ポイントがローカルコンピューター上に作成されます。

システムの復元ポイントと `Checkpoint-Computer` コマンドレットは、windows 8、windows 7、Windows Vista、WINDOWS XP などのクライアントオペレーティングシステムでのみサポートされています。

Windows 8 以降では、1日に複数の `Checkpoint-Computer` チェックポイントを作成することはできません。

## 例

### 例 1: システムの復元ポイントを作成する

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

このコマンドは、Install MyApp というシステム復元ポイントを作成します。
復元ポイントの種類には、既定値の APPLICATION_INSTALL を使用します。

### 例 2: システム MODIFY_SETTINGS の復元ポイントを作成する

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

このコマンドは、"ChangeNetSettings" という名前の MODIFY_SETTINGS システム復元ポイントを作成します。

## PARAMETERS

### -Description

復元ポイントのわかりやすい名前を指定します。
このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorePointType

復元ポイントの種類を指定します。
既定値は APPLICATION_INSTALL です。

このパラメーターの有効値は、次のとおりです。

- APPLICATION_INSTALL
- APPLICATION_UNINSTALL
- DEVICE_DRIVER_INSTALL
- MODIFY_SETTINGS
- CANCELLED_OPERATION

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### なし

パイプを使用してオブジェクトをにパイプすることはできません `Checkpoint-Computer` 。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

- このコマンドレットは、 **Systemrestore** クラスの **Createrestorepoint** メソッドを **BEGIN_SYSTEM_CHANGE** イベントと共に使用します。
- Windows 8 以降では、1日に複数の `Checkpoint-Computer` システム復元ポイントを作成することはできません。 24 時間が経過する前に新しい復元ポイントを作成しようとすると、Windows PowerShell によって次のエラーが生成されます。

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## 関連リンク

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restore-Computer](Restore-Computer.md)
