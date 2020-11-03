---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 08c9d61f210761e2ed7a3a5014812b2bd362201b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213536"
---
# Enable-WSManTrace

## 概要
WSMan プロバイダーが有効になっているログセッションを開始します。

## SYNTAX

```
Enable-WSManTrace [<CommonParameters>]
```

## Description
このコマンドレットは、WSMan プロバイダーが有効になっているログセッションを開始します。 次のイベントプロバイダーが有効になっています。

- イベント転送
- IpmiDrv
- IPMIPrv
- WinRM
- WinrsCmd
- WinrsExe
- WinrsMgr
- WSManProvHost

セッションの名前は ' wsmlog ' です。

このコマンドレットは、コマンドレットを使用し `Start-Trace` ます。

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 例

### 例 1: WSMan ログセッションを開始します。

```powershell
Enable-WSManTrace
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

[Start-Trace](start-trace.md)

[Disable-WSManTrace](Disable-WSManTrace.md)
