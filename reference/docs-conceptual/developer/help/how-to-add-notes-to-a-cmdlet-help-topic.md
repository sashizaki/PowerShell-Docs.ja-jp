---
title: コマンドレットのヘルプ トピックに注を追加する方法
ms.date: 10/20/2020
ms.openlocfilehash: 7f8be34a82de2c12cfd2a05deed139ddb30da95f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "92298305"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに注を追加する方法

このセクションでは、PowerShell コマンドレットのヘルプ トピックに**注**セクションを追加する方法について説明します。 **注**セクションは、パラメーターの詳細な説明など、他の構造化されたセクションには当てはまりにくい詳細を説明するために使用します。 その内容には、特定のプロバイダーでのコマンドレットの動作、コマンドレットの独自かつ重要な使用方法、または想定されるエラー条件の回避方法に関するコメントなどを含めることができます。

**注**セクションは、1 つの `<maml:alertset>` ノードを使用して定義されます。 注セクションに追加できる注の数に制限はありません。 注ごとに、`<maml:alertset>` ノードに `<maml:alert>` タグのペアを追加します。 それぞれの注の内容は、一連の `<maml:para>` タグ内に追加します。 スペースに対しては空の `<maml:para>` タグを使用します。

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```
