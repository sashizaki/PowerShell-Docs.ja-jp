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
ms.openlocfilehash: f2f319a3cab4b4bd91e9b634dda57d58a6476b62
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854738"
---
# <a name="how-to-test-updatable-help"></a>更新可能なヘルプをテストする方法

このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。

## <a name="using-verbose-to-detect-errors"></a>エラーを検出する詳細な使用

HelpInfo XML ファイルと、モジュール用の CAB ファイルをアップロードした後、ファイルをテストを実行して、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドと、 **Verbose**パラメーター。 **Verbose**パラメーター`Update-Help`読み取りから、その操作で重要な手順を報告する、 **HelpInfoUri**アンパックされた CAB ファイルのファイルの種類を検証するモジュール マニフェストでキー言語固有のモジュール ディレクトリにファイルを配置します。
HelpInfo XML ファイルと、モジュール用の CAB ファイルをアップロードした後、ファイルをテストを実行して、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドと、 **Verbose**パラメーター。 **Verbose**パラメーター`Update-Help`読み取りから、その操作で重要な手順を報告する、 **HelpInfoUri**アンパックされた CAB ファイルのファイルの種類を検証するモジュール マニフェストでキー言語固有のモジュール ディレクトリにファイルを配置します。

すべての詳細なメッセージが解決された場合は、実行、`Update-Help`コマンドと、**デバッグ**パラメーター。 このパラメーターは、更新可能なヘルプ ファイルの残りの問題を検出する必要があります。