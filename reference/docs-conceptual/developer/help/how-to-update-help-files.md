---
title: ヘルプ ファイルを更新する方法
ms.date: 09/12/2016
ms.openlocfilehash: 80f7c8865729515de98648765fa36ce540e00162
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892950"
---
# <a name="how-to-update-help-files"></a>ヘルプ ファイルを更新する方法

このトピックでは、更新可能なヘルプをサポートするモジュールのヘルプファイルを更新する方法について説明します。

## <a name="updating-help-files"></a>ヘルプファイルの更新

ヘルプファイルの更新には、エラーの修正、概念の明確化、よく寄せられる質問への回答、新しいファイルの追加、新しい例の追加など、さまざまな理由があります。

ヘルプファイルを更新するには:

1. ファイルを変更します。
1. ファイルを他の UI カルチャに変換します。
1. 各 UI カルチャのモジュールについて、すべてのヘルプファイル (新規、変更済み、および変更されていない) を収集します。
1. XML スキーマに対してファイルを検証します。
1. 各 UI カルチャの CAB ファイルをリビルドします。
1. HelpInfo XML ファイルで、各 UI カルチャの CAB ファイルのバージョン番号をインクリメントします。
1. HelpInfo XML ファイルの**Helpcontenturi**要素の値によって指定された場所に新しい CAB ファイルをアップロードします。 古い CAB ファイルを新しい CAB ファイルに置き換えます。
1. 更新された HelpInfo XML ファイルを、モジュールマニフェストの**Helpinfouri**キーによって指定された場所にアップロードします。 古い HelpInfo XML ファイルを新しいファイルに置き換えます。
