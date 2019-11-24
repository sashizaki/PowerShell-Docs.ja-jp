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
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361271"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに注を追加する方法

このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックにメモセクションを追加する方法について説明します。 メモセクションは、パラメーターの詳細な説明など、他の構造化されたセクションに簡単に適合しない詳細を説明するために使用されます。 このコンテンツには、特定のプロバイダーを使用したコマンドレットの動作、一意であることが重要なコマンドレットの使用方法、またはエラー状態の発生を回避する方法に関するコメントが含まれる場合があります。

メモセクションに追加できるノートの数に制限はありません。 メモごとに、maml: alert > タグのペアを \<maml: alertset > ノードに追加 \<ます。 各ノートの内容は \<maml: 段落 > タグのセット内に追加されます。 スペースには、空白の \<maml: 段落 > タグを使用します。

次の XML は、\<maml: alertset > ノードと2つのメモを示しています。 各ノートにはオプションの \<maml: title > タグがあります (タイトルは、\<maml: alert > タグの任意のセットをグループ化するために使用できます)。また、各ノートには、スペースのコンテンツの後に空白行があることに注意してください。

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



