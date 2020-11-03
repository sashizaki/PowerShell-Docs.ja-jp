---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 90cb571f93243e6fbc59970e5602911e17e25ec7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213547"
---
# Disable-WSManTrace

## 概要
有効にする-WSManTrace によって開始された WSMan ログセッションを停止します。

## SYNTAX

```
Disable-WSManTrace [<CommonParameters>]
```

## Description
このコマンドレットは、Enable-WSManTrace によって開始された WSMan ログセッションを停止します。

このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 例

### 例 1: WSMan トレースを停止する

```powershell
Disable-WSManTrace
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

[Enable-WSManTrace](Enable-WSManTrace.md)
