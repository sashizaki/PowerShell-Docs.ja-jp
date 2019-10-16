---
title: データを表示するための条件を定義する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1e05821-6aec-437b-84a5-218a5727f88b
caps.latest.revision: 10
ms.openlocfilehash: 8a5b84b6a461e9fc340a5981578d95ca2ac6b9f7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363901"
---
# <a name="defining-conditions-for-displaying-data"></a>データの表示条件を定義する

ビューまたはコントロールによって表示されるデータを定義するときに、表示されるデータに必要な条件を指定できます。 条件は、特定のプロパティによって、またはスクリプトまたはプロパティの値が `true` に評価されるときにトリガーされます。 選択条件が満たされると、ビューまたはコントロールの定義が使用されます。

## <a name="specifying-a-selection-condition-for-a-definition"></a>定義の選択条件の指定

ビューまたはコントロールの定義を作成するときに、`EntrySelectedBy` 要素を使用して、定義を使用するオブジェクトまたは定義を使用するために必要な条件を指定します。 条件は `SelectionCondition` 要素によって指定されます。

次の例では、テーブルビューの定義に対して選択条件が指定されています。 この例では、指定されたスクリプトが `true` に評価される場合にのみ、定義が使用されます。

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

ビューまたはコントロールの定義に指定できる選択条件の数に制限はありません。 唯一の要件は次のとおりです。

- 選択条件では、条件をトリガーするプロパティ名またはスクリプトを1つ指定する必要がありますが、両方を指定することはできません。

- 選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。

## <a name="specifying-a-selection-condition-for-an-item"></a>項目の選択条件の指定

項目定義に `ItemSelectionCondition` 要素を含めることによって、リストビューまたはコントロールの項目をいつ使用するかを指定することもできます。 次の例では、リストビューの項目に対して選択条件が指定されています。 この例では、この項目は、スクリプトが `true` に評価された場合にのみ使用されます。

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

項目の選択条件は1つだけ指定できます。 条件では、条件をトリガーするプロパティ名またはスクリプトを1つ指定する必要がありますが、両方を指定することはできません。

## <a name="xml-elements"></a>XML 要素

 次の XML 要素を使用して、選択条件を作成します。

- 次の要素は、ビュー定義の選択条件を指定します。

    - [TableControl の EntrySelectedBy の SelectionCondition 要素 (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [ListControl (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [WideControl (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [CustomControl (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- 次の要素は、共通およびビューのコントロール定義の選択条件を指定します。

    - [構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- 次の要素は、コレクションオブジェクトを展開するための選択条件を指定します。

    - [列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- 次の要素は、新しいデータグループを表示するための選択条件を指定します。

    - [GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- 次の要素は、リストビューの項目選択条件を指定します。

    - [ListControl の ListItem の ItemSelectionCondition 要素 (形式)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- 次の要素は、コントロールの項目選択条件を指定します。

    - [構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [CustomControl (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>参照

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
