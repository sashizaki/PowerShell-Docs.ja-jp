---
description: PowerShell で収集されたテレメトリと、オプトアウトする方法について説明します。
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: ef921d0feefe277c2832c0a459ae150c9a6b4acb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222339"
---
# <a name="about-telemetry"></a>テレメトリについて

## <a name="short-description"></a>概要

PowerShell で収集されたテレメトリと、オプトアウトする方法について説明します。

## <a name="long-description"></a>詳細説明

PowerShell は、基本的なテレメトリデータを Microsoft に送信します。
このデータにより、PowerShell が使用されている環境をより深く理解し、新機能と修正の優先順位を付けることができます。
次のテレメトリポイントが記録されます。

- PowerShell の種類で開始 (API vs コンソール)
- 一意の PowerShell 使用状況のカウント
- 次の実行の種類の数。
  - アプリケーション (ネイティブコマンド)
  - ExternalScript
  - スクリプト
  - 機能
  - コマンドレット
- PowerShell に付属している、Microsoft が所有する試験的な機能または試験的な機能の数
- ホストされているセッションの数
- Microsoft 所有のモジュールが読み込まれた回数

このデータには、OS 名、OS バージョン、PowerShell のバージョン、および配布チャネルが含まれます。

このテレメトリをオプトアウトするには、環境変数 POWERSHELL_TELEMETRY_OPTOUT を true、yes、または1に設定します。

