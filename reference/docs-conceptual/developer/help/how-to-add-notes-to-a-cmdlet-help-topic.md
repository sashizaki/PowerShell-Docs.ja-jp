---
title: コマンドレットのヘルプ トピックに注を追加する方法
ms.date: 09/12/2016
ms.openlocfilehash: d3679126ea34d7e86bcda700d0d050d8312a7aa2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893409"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに注を追加する方法

このセクションでは、PowerShell コマンドレットのヘルプトピックに**メモ**セクションを追加する方法について説明します。 **メモ**セクションは、パラメーターの詳細な説明など、他の構造化されたセクションに簡単に適合しない詳細を説明するために使用されます。 このコンテンツには、特定のプロバイダーを使用したコマンドレットの動作、一意であることが重要なコマンドレットの使用方法、またはエラー状態の発生を回避する方法に関するコメントが含まれる場合があります。

メモセクションに追加できるノートの数に制限はありません。 各ノートについて、ノードに1組のタグを追加し `<maml:alert>` `<maml:alertset>` ます。 各ノートの内容は、一連のタグ内に追加され `<maml:para>` ます。 空白 `<maml:para>` タグをスペースに使用します。

次の XML は、 `<maml:alertset>` 2 つのノートを持つノードを示しています。 各メモには省略可能な `<maml:title>` タグ (タイトルを使用してタグのセットをグループ化することができます) があり、各ノートには、 `<maml:alert>` スペースのコンテンツの後に空白行があることに注意してください。

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
