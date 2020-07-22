---
title: 更新可能なヘルプをテストする方法
ms.date: 09/12/2016
ms.openlocfilehash: 0602349f853fddd0cadae545eaf0302c150e3a28
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892967"
---
# <a name="how-to-test-updatable-help"></a>更新可能なヘルプをテストする方法

このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。

## <a name="using-verbose-to-detect-errors"></a>Verbose を使用してエラーを検出する

モジュールの HelpInfo XML ファイルと CAB ファイルをアップロードしたら、 **Verbose**パラメーターを指定して[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドを実行し、ファイルをテストします。 **Verbose**パラメーターは、 `Update-Help` アクションの重要なステップを報告するように指示します。これには、モジュールマニフェストの**helpinfouri**キーを読み取って、展開された CAB ファイル内のファイルの種類を検証し、それらのファイルを言語固有のモジュールディレクトリに配置します。

すべての詳細メッセージを解決したら、 `Update-Help` **Debug**パラメーターを指定してコマンドを実行します。
このパラメーターは、更新可能なヘルプファイルに関する残りの問題を検出する必要があります。
