---
external help file: PSReadLine-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: 2dee8287558e9d5c001000fc5a57a859febee1a3
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224728"
---
# PSConsoleHostReadLine

## 概要
この関数は、PSReadLine のメインエントリポイントです。

## SYNTAX

```
PSConsoleHostReadLine
```

## Description

`PSConsoleHostReadLine` は、PSReadLine モジュールのメインエントリポイントです。 PowerShell コンソールホストは、PSReadLine モジュールを自動的に読み込み、この関数を呼び出します。 通常の動作状況では、この関数はコマンドラインから使用するためのものではありません。

拡張ポイント `PSConsoleHostReadLine` は、コンソールホストに特別な意味を持ちます。 ホストは、この名前を持つ任意のエイリアス、関数、またはスクリプトを呼び出します。 PSReadLine は、コンソールホストから呼び出されるように、この関数を定義します。

## 例

### 例 1

この関数は、コマンドラインから使用するためのものではありません。

## PARAMETERS

## 入力

### なし

## 出力

### なし

## 注

## 関連リンク

[about_PSReadLine](./About/about_PSReadLine.md)
