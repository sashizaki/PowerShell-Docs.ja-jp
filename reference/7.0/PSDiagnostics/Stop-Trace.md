---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 2629ae1beb722282065e76600174b511bfe5fbc9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211115"
---
# Stop-Trace

## 概要
イベントトレースログセッションを停止します。

## SYNTAX

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## Description

このコマンドレットは、Windows イベントトレースのログセッションを停止します。

このコマンドレットは、次のコマンドレットによって使用されます。

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 例

### 例 1: WSMan トレースログセッションを停止する

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## PARAMETERS

### -/
イベントを保存またはスケジュールせずに直接イベントトレースセッションに送信します。

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

### -セッション名
停止するイベントトレースセッションの名前。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

## 出力

### なし

## 注

## 関連リンク

[イベントのトレース](/windows/desktop/ETW/event-tracing-portal)

[Start-Trace](start-trace.md)

[Disable-PSWSManCombinedTrace](Disable-PSWSManCombinedTrace.md)

[Disable-WSManTrace](Disable-WSManTrace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)

[Enable-WSManTrace](Enable-WSManTrace.md)
