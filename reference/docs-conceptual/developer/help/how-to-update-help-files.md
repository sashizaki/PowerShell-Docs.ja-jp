---
title: ヘルプファイルを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 35b3fd696419d0135fd6f662223e6c8586df443a
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811651"
---
# <a name="how-to-update-help-files"></a>ヘルプ ファイルを更新する方法

このトピックでは、更新可能なヘルプをサポートするモジュールのヘルプファイルを更新する方法について説明します。

## <a name="updating-help-files"></a>ヘルプファイルの更新

ヘルプファイルの更新には、エラーの修正、概念の明確化、よく寄せられる質問への回答、新しいファイルの追加、新しい例の追加など、さまざまな理由があります。

ヘルプファイルを更新するには:

1. ファイルを変更します。

2. ファイルを他の UI カルチャに変換します。

3. 各 UI カルチャのモジュールについて、すべてのヘルプファイル (新規、変更済み、および変更されていない) を収集します。

4. XML スキーマに対してファイルを検証します。

5. 各 UI カルチャの CAB ファイルをリビルドします。

6. HelpInfo XML ファイルで、各 UI カルチャの CAB ファイルのバージョン番号をインクリメントします。

7. HelpInfo XML ファイルの**Helpcontenturi**要素の値によって指定された場所に新しい CAB ファイルをアップロードします。 古い CAB ファイルを新しい CAB ファイルに置き換えます。

8. 更新された HelpInfo XML ファイルを、モジュールマニフェストの**Helpinfouri**キーによって指定された場所にアップロードします。 古い HelpInfo XML ファイルを新しいファイルに置き換えます。
