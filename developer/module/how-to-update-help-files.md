---
title: ヘルプ ファイルを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 2c1fbd70aab1f65f33ea206b7ab1e2bd3dfd8c7a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855528"
---
# <a name="how-to-update-help-files"></a>ヘルプ ファイルを更新する方法

このトピックでは、更新可能なヘルプをサポートするモジュールのヘルプ ファイルを更新する方法について説明します。

## <a name="updating-help-files"></a>ヘルプ ファイルを更新しています

エラーを修正、概念を明確化、よく寄せられる質問に答えの新しいファイルを追加する新しいより良い例の追加などのヘルプ ファイルを更新する多くの理由があります。

ヘルプ ファイルを更新します。

1. ファイルを変更します。

2. ファイルを他の UI カルチャに翻訳します。

3. すべてのヘルプ ファイル (新しい、変更、および変更されていない) 各 UI カルチャでモジュールを収集します。

4. XML スキーマに対してファイルを検証します。

5. 各 UI カルチャ用の CAB ファイルを再構築します。

6. HelpInfo XML ファイルでは、各 UI カルチャ用の CAB ファイルのバージョン番号をインクリメントします。

7. 値によって指定されている場所に新しい CAB ファイルをアップロード、 **HelpContentUri** HelpInfo XML ファイル内の要素。 以前の CAB ファイルを新しい CAB ファイルに置き換えます。

8. 指定された場所に更新された HelpInfo XML ファイルをアップロード、 **HelpInfoUri**モジュール マニフェストでキー。 古い HelpInfo XML ファイルを新しいファイルに置き換えます。