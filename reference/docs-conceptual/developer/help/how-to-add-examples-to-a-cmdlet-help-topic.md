---
title: 例をコマンドレットに追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: 82bee7b7bb0ef49203636f2a293075f3db924ce4
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557092"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに例を追加する方法

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>コマンドレットのヘルプの例について理解しておくべきこと

- パラメーター名が省略可能な場合でも、コマンド内のすべてのパラメーター名を一覧表示します。 これにより、ユーザーがコマンドを簡単に解釈できるようになります。

- Windows PowerShell®で動作する場合でも、エイリアスと部分的なパラメーター名は避けてください。

- この例では、コマンドの構築のための有理数について説明します。 特定のパラメーターと値を選択した理由、および変数の使用方法について説明します。

- コマンドで式を使用する場合は、詳細について説明します。

- コマンドでオブジェクトのプロパティとメソッド (特に既定の表示に表示されないプロパティ) を使用する場合は、オブジェクトについてユーザーに通知する機会として例を使用します。

## <a name="help-views-that-display-examples"></a>例を表示するヘルプビュー

例は、コマンドレットのヘルプの詳細ビューと完全ビューでのみ表示されます。

## <a name="adding-an-examples-node"></a>例ノードの追加

次の XML は、1つの例のノードを含む例ノードを追加する方法を示しています。 トピックに含める例ごとに、その他の例のノードを追加します。

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>例のタイトルの追加

次の XML は、この例のタイトルを追加する方法を示しています。 タイトルは、例を他の例とは別に設定するために使用されます。 Windows PowerShell®では、連番のサンプル番号を含む標準ヘッダーが使用されます。

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>追加 (前の文字を)

次の XML は、例のコマンドの直前に表示される、Windows PowerShell プロンプトなどの文字を追加する方法を示しています (スペースは不要です)。 Windows PowerShell®では、Windows PowerShell プロンプト: C:\ PS> が使用されます。

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

## <a name="adding-the-command"></a>コマンドの追加

次の XML は、例の実際のコマンドを追加する方法を示しています。 コマンドを追加するときに、コマンドレットとパラメーターの名前全体 (エイリアスを使用しない) を入力します。 また、可能な限り小文字を使用します。

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

次の XML は、この例の説明を追加する方法を示しています。 Windows PowerShell®では、複数の \< \< maml: 段落> タグを使用することもできますが、説明のために maml: 段落> タグの1つのセットを使用します。

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

## <a name="adding-example-output"></a>出力例の追加

次の XML は、コマンドの出力を追加する方法を示しています。 コマンドの結果情報は省略可能ですが、場合によっては、特定のパラメーターを使用した場合の影響を示すのに役立ちます。 Windows PowerShell®では、コマンドの \< 出力をコマンドから分離するために、2つの空白の maml: 段落> タグを使用します。

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
