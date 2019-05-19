---
title: コマンドレットのヘルプ トピックの例を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: b6f8aef76a5f4b5dc1a60425541856ead9a9c77a
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855127"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに例を追加する方法

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>コマンドレットのヘルプの例について知っておくべきこと

- パラメーター名は省略可能な場合でも、すべてのコマンドでパラメーター名の一覧を表示します。 これにより、ユーザーがコマンドを簡単に解釈できます。

- Windows PowerShell® で作業する場合でも、エイリアスと部分的なパラメーターの名前をしないでください。

- 例の説明で合理的なコマンドを構築するための手順を説明します。 特定のパラメーターと値を選択した理由と、変数を使用する方法について説明します。

- コマンドは、式を使用している場合は、詳細に説明します。

- コマンドは、既定の表示に表示されないプロパティ特に、オブジェクトのプロパティとメソッドを使用している場合は、営業案件に、オブジェクトについて、ユーザーに通知するよう、例を使用します。

## <a name="help-views-that-display-examples"></a>例を表示するビューについてのヘルプ

例については、コマンドレットのヘルプの詳細と完全なビューでのみ表示されます。

## <a name="adding-an-examples-node"></a>例として、ノードを追加します。

次の XML では、1 つのノードの例を含む例ノードを追加する方法を示します。 各例については、トピックに追加するその他の例のノードを追加します。

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>例のタイトルを追加します。

次の XML では、例では、タイトルを追加する方法を示します。 タイトルは、その他の例とは別の例の設定に使用されます。 Windows PowerShell® では、逐次の例の番号を含む標準ヘッダーを使用します。

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>文字の前の追加

次の XML では、介在するスペース) を含めずコマンドの例の直前に表示される、Windows PowerShell プロンプトなどの文字を追加する方法を示します。 Windows PowerShell® では、Windows PowerShell プロンプトを使用します。C:\PS &GT;。

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
</command:example>
</command:examples>
```

## <a name="adding-the-command"></a>コマンドを追加します。

次の XML では、実際の例では、コマンドを追加する方法を示します。 コマンドを追加する場合は、全体の名前を入力 (エイリアスは使用されません) のコマンドレットとパラメーター。 また、可能であれば小文字の文字を使用します。

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
</command:example>
</command:examples>
```

## <a name="adding-a-description"></a>説明の追加

次の XML では、この例の説明を追加する方法を示します。 Windows PowerShell® の 1 つのセットを使用して\<maml:para > 場合でも、説明のタグ複数\<maml:para > タグを使用できます。

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
    </dev:remarks>
</command:example>
</command:examples>
```

## <a name="adding-example-output"></a>出力例を追加します。

次の XML では、コマンドの出力を追加する方法を示します。 コマンドの結果の情報は省略可能では、場合によっては、特定のパラメーターを使用しての効果を付けると便利です。 Windows PowerShell® が空白の 2 つのセットを使用して\<maml:para > タグからのコマンドは、コマンドの出力を分離します。

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
      <maml:para></maml:para>
      <maml:para></maml:para>
      <maml:para> command output </maml:para>
</dev:remarks>
</command:example>
</command:examples>
```