---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0f1173cbfab139438d55ff49272f9625579820dc
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211347"
---
# Unregister-PSRepository

## 概要
リポジトリの登録を解除します。

## SYNTAX

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## Description

`Unregister-PSRepository`コマンドレットは、現在のユーザーのリポジトリを登録解除します。

## 例

### 例 1: リポジトリの登録を解除する

この例では、myNuGetSource という名前のリポジトリを登録解除します。

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### 例 2: すべてのリポジトリの登録を解除する

この例では `Get-PSRepository` 、を使用して登録されているすべてのリポジトリを取得し、パイプライン演算子を使用してそれらをに渡して、登録を `Unregister-PSRepository` 解除します。

```powershell
Get-PSRepository | Unregister-PSRepository
```

## PARAMETERS

### -Name

削除するリポジトリの名前の配列を指定します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.String[]

## 出力

### System.Object

## 注

## 関連リンク

[Get-PSRepository](Get-PSRepository.md)

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)
