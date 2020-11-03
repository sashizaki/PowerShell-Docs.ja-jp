---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f67b5d9fe8da48cca5fd4ec7d2056a4702d3ff16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213539"
---
# Enable-PSWSManCombinedTrace

## 概要
WSMan プロバイダーと PowerShell プロバイダーが有効になっている状態で、ログセッションを開始します。

## SYNTAX

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## Description

このコマンドレットは、次の PowerShell プロバイダーが有効になっているログセッションを開始します。

- Microsoft-Windows-PowerShell
- Microsoft-Windows-WinRM

セッションの名前は ' PSTrace ' です。

このコマンドレットは、コマンドレットを使用し `Start-Trace` ます。

このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。

## 例

### 例 1: 結合されたログセッションを開始する

```powershell
Enable-PSWSManCombinedTrace
```

## PARAMETERS

### -DoNotOverwriteExistingTrace

既定では、イベントは "$pshome \Traces\PSTrace.etl" に書き込まれます。 このパラメーターを使用すると、コマンドレットによって一意のファイル名 "$pshome \Traces\ PSTrace_ {guid} .etl" が作成されます。

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

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

## 出力

### System.Object

## 注

## 関連リンク

[イベントのトレース](/windows/desktop/ETW/event-tracing-portal)

[Start-Trace](start-trace.md)

[Disable-PSWSManCombinedTrace](Disable-PSWSManCombinedTrace.md)
