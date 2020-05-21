---
title: 更新可能なヘルプのテスト方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: 8dd3770a60ca56634ad1eb1ac8cf89d96c975c90
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560510"
---
# <a name="how-to-test-updatable-help"></a>更新可能なヘルプをテストする方法

このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。

## <a name="using-verbose-to-detect-errors"></a>Verbose を使用してエラーを検出する

モジュールの HelpInfo XML ファイルと CAB ファイルをアップロードしたら、 **Verbose**パラメーターを指定して[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドを実行し、ファイルをテストします。 **Verbose**パラメーターは、 `Update-Help` アクションの重要なステップを報告するように指示します。これには、モジュールマニフェストの**helpinfouri**キーを読み取って、展開された CAB ファイル内のファイルの種類を検証し、それらのファイルを言語固有のモジュールディレクトリに配置します。

すべての詳細メッセージを解決したら、 `Update-Help` **Debug**パラメーターを指定してコマンドを実行します。 このパラメーターは、更新可能なヘルプファイルに関する残りの問題を検出する必要があります。
