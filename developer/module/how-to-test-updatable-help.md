---
title: 更新可能なヘルプをテストする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794265"
---
# <a name="how-to-test-updatable-help"></a>更新可能なヘルプをテストする方法

このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。

## <a name="using-verbose-to-detect-errors"></a>エラーを検出する詳細な使用

HelpInfo XML ファイルと、モジュール用の CAB ファイルをアップロードした後、ファイルをテストを実行して、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドと、 **Verbose**パラメーター。 **Verbose**パラメーター`Update-Help`読み取りから、その操作で重要な手順を報告する、 **HelpInfoUri**アンパックされた CAB ファイルのファイルの種類を検証するモジュール マニフェストでキー言語固有のモジュール ディレクトリにファイルを配置します。

すべての詳細なメッセージが解決された場合は、実行、`Update-Help`コマンドと、**デバッグ**パラメーター。 このパラメーターは、更新可能なヘルプ ファイルの残りの問題を検出する必要があります。