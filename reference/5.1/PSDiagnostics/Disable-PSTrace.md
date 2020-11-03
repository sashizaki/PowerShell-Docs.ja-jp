---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: fc58e0bcfdd0b4ee7c7ee383b44f7d7f428c34c0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213563"
---
# Disable-PSTrace

## 概要
Microsoft Windows PowerShell イベントプロバイダーのログを無効にします。

## SYNTAX

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## Description

このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを無効にします。

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 例

### 例 1: PowerShell の分析イベントログを無効にする

次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを無効にします。

```powershell
Disable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -分析のみ

このパラメーターを使用すると、コマンドレットは、Microsoft Windows PowerShell プロバイダーの分析イベントログを無効にします。 操作イベントログは変更されません。

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

## 入力

### なし

## 出力

### System.Object

## 注

このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 関連リンク

[Get-LogProperties](Get-LogProperties.md)

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)
