---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 4a98941de072b9b57b89a25bc180c0ee391d8b63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213560"
---
# Disable-PSWSManCombinedTrace

## 概要
-Pswsman結合 Edtrace を有効にして、ログセッションを開始します。

## SYNTAX

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## Description

このコマンドレットは、によって開始されたログセッションを停止 `Enable-PSWSManCombinedTrace` します。

このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 例

### 例 1: 結合されたログセッションを無効にする

```powershell
Disable-PSWSManCombinedTrace
```

## PARAMETERS

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

## 出力

### System.Object

## 注

## 関連リンク

[イベントのトレース](/windows/desktop/ETW/event-tracing-portal)

[Stop-Trace](stop-trace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)
