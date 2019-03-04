---
title: コマンドレットのヘルプ トピックにメモを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862268"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに注を追加する方法

このセクションでは、Windows PowerShell® コマンドレットのヘルプ トピックをノートのセクションを追加する方法について説明します。 ノートのセクションは、パラメーターの詳細な説明など、他の構造化されたセクションに簡単に適合しない詳細の説明に使用されます。 このコンテンツは、特定のプロバイダーとコマンドレットがどのように連携するか、コマンドレット、またはエラー状況を回避する方法のいくつか一意、ながらも重要なの使用に関するコメントを含めることができます。

ノートのセクションに追加できるノートの数に制限はありません。 各のメモの追加のペア\<maml:alert > タグを\<maml:alertset > ノード。 各メモの内容は、一連の追加\<maml:para > タグです。 使用して空白\<maml:para > タグの間隔をします。

次の XML に示します、 \<maml:alertset > ノードに 2 つのメモ。 各メモが省略可能なことに注意してください\<maml:title > タグ (タイトルは、任意のセットをグループ化に使用できる\<maml:alert > タグ)、および間隔のコンテンツを次の空白行が各に注意してください。

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



