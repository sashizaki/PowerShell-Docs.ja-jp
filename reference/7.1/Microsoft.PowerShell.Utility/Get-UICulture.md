---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 3e1ae99f3e2bd52d26e9c567fcc8184b07c71a4a
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209297"
---
# Get-UICulture

## 概要
オペレーティングシステムの現在の UI カルチャ設定を取得します。

## SYNTAX

```
Get-UICulture [<CommonParameters>]
```

## Description

`Get-UICulture`コマンドレットは、Windows の現在のユーザーインターフェイス (UI) カルチャ設定に関する情報を取得します。
UI カルチャは、どのテキスト文字列がメニューやメッセージなどのユーザー インターフェイス要素に使用されるかを決定します。

また、コマンドレットを使用して、 `Get-Culture` システム上の現在のカルチャを取得することもできます。
カルチャは、数値、通貨、日付などの項目の表示形式を決定します。

## 例

### 例 1: UI カルチャを取得する

```powershell
Get-UICulture
```

このコマンドは、現在の UI カルチャの情報を取得します。

### 例 2: UI カルチャを取得し、結果の書式を設定する

```powershell
Get-UICulture | Format-List *
```

このコマンドは、現在の UI カルチャのプロパティのすべての値を一覧表示します。

### 例 3: Calendar プロパティの値を取得する

```powershell
(Get-UICulture).Calendar
```

このコマンドは、現在の UI カルチャの **Calendar** プロパティの現在の値を表示します。
カレンダーは、UI カルチャのプロパティの 1 つにすぎません。
すべてのプロパティを表示するには、「」と入力 `Get-UICulture | Get-Member` します。

### 例 4: 短い日付パターンを取得する

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

このコマンドは、現在の UI カルチャの短い形式の日付パターンを表示します。
UI カルチャの **DateTimeFormat** プロパティのすべてのサブプロパティを表示するには、「」と入力 `(Get-UICulture).DateTimeFormat | gm` します。

## PARAMETERS

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### なし

パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### VistaCultureInfo, Microsoft. PowerShell...

`Get-UICulture` 現在の UI カルチャを表すオブジェクトを返します。
Windows PowerShell 3.0 では、 **CultureInfo** オブジェクトを返します。
Windows PowerShell 2.0 では、 **VistaCultureInfo** オブジェクトが返されます。

## 注

- 変数および変数を使用することもでき `$PsCulture` `$PsUICulture` ます。 変数には `$PsCulture` 現在のカルチャの名前が格納され、変数には `$PsUICulture` 現在の UI カルチャの名前が格納されます。

## 関連リンク

