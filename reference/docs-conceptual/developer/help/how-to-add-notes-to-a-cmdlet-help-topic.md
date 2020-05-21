---
title: コマンドレットにメモを追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 1a365a167c245006bb882a542aedb5c43cfc4c96
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557109"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに注を追加する方法

このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックにメモセクションを追加する方法について説明します。 メモセクションは、パラメーターの詳細な説明など、他の構造化されたセクションに簡単に適合しない詳細を説明するために使用されます。 このコンテンツには、特定のプロバイダーを使用したコマンドレットの動作、一意であることが重要なコマンドレットの使用方法、またはエラー状態の発生を回避する方法に関するコメントが含まれる場合があります。

メモセクションに追加できるノートの数に制限はありません。 メモごとに、 \< maml: alert> タグのペアを \< maml: alertset> ノードに追加します。 各ノートの内容は、一連の \< maml: 段落> タグ内に追加されます。 \<スペースには、空白の maml: 段落> タグを使用します。

次の XML は、 \< maml: alertset> ノードと2つの注意点を示しています。 各メモにはオプションの \< maml: title> タグがあります (タイトルは、任意の maml: alert> タグのセットをグループ化するために使用できます \< )。また、各ノートには、スペースのコンテンツの後に空白行があることに注意してください。

```xml
<maml:alertSet>
  <maml:title>title for Note 1</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
  <maml:title>title for Note 2</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
</maml:alertSet>
```
