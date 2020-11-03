---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 0f076d21ce590b4f1d3eb5b06e891d753dbea638
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209108"
---
# Exit-PSHostProcess

## 概要
ローカルプロセスで対話型セッションを終了します。

## SYNTAX

```
Exit-PSHostProcess [<CommonParameters>]
```

## Description

**Enter-pshostprocess** コマンドレットは、Enter-PSHostProcess コマンドレットを実行して、開いたローカルプロセスとの対話型セッションを終了します。 プロセス内で実行されているスクリプトのデバッグまたはトラブルシューティングが完了したら、プロセス内から **enter-pshostprocess** コマンドレットを実行します。

## 例

### 例 1: プロセスを終了する

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

この例では、「Enter-pshostprocess」で説明されているように、プロセス内の実行空間で実行されているスクリプトをデバッグするために、アクティブプロセスで作業しています。 デバッガーを終了する **終了** コマンドを入力した後、 **enter-pshostprocess** コマンドレットを実行して、プロセスとの対話型セッションを終了します。
このコマンドレットは、プロセス内のセッションを閉じ、PS C: プロンプトに戻り \\ \> ます。

## PARAMETERS

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

## 出力

## 注

## 関連リンク

[Enter-PSHostProcess](Enter-PSHostProcess.md)
