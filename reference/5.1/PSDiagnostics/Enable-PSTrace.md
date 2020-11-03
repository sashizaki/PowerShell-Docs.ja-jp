---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 9abc91086d42ec7b813695e241820947f7fb0acc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213544"
---
# Enable-PSTrace

## 概要
Microsoft Windows PowerShell イベントプロバイダーのログを有効にします。

## SYNTAX

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## Description

このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを有効にします。

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 例

### 例 1: PowerShell の分析イベントログを有効にする

次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを有効にします。

```powershell
Enable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -分析のみ

このパラメーターを使用すると、コマンドレットによって、Microsoft Windows PowerShell プロバイダーの分析イベントログが有効になります。 操作イベントログは変更されません。

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

### -Force

プロンプトを表示せずに変更を強制するために使用します。

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

[Disable-PSTrace](Disable-PSTrace.md)
