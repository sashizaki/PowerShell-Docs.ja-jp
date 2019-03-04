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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855648"
---
# <a name="defining-conditions-for-displaying-data"></a>データの表示条件を定義する

ビューまたはコントロールを表示するデータを定義するときは、データを表示するのに必要な条件を指定できます。 ときに、スクリプトまたは特定のプロパティによって、条件がトリガーされることができます、プロパティの値として評価または`true`します。 選択条件が満たされたときに、ビューまたはコントロールの定義が使用されます。

## <a name="specifying-a-selection-condition-for-a-definition"></a>定義の選択条件を指定します。

ビューまたはコントロールの定義を作成するときに、`EntrySelectedBy`要素を使用して、オブジェクトの定義が使用または使用する定義の条件が存在する必要がありますを指定します。 条件が指定された、`SelectionCondition`要素。

次の例では、選択条件を指定して、テーブル ビューの定義についてはします。 この例で定義を使用する、指定したスクリプトが評価されるときにのみ`true`します。

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

ビューまたはコントロールの定義に指定できる選択条件の数に制限はありません。 唯一の要件は、次のとおりです。

- 選択条件では、1 つのプロパティ名またはスクリプトを起動するトリガーの条件を指定する必要がありますが、両方を指定することはできません。

- 選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。

## <a name="specifying-a-selection-condition-for-an-item"></a>項目の選択条件を指定します。

含めることによってリスト ビューまたはコントロールの項目を使用する場合を指定することも、`ItemSelectionCondition`アイテム定義内の要素。 次の例では、選択条件を指定して、リスト ビューの項目の。 この例で、項目を使用するスクリプトが評価される場合にのみ`true`します。

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

項目の 1 つだけ選択条件を指定できます。 条件が 1 つのプロパティ名またはスクリプトを起動するトリガーの条件を指定する必要がありますが、両方を指定することはできません。

## <a name="xml-elements"></a>XML 要素

 次の XML 要素を使用して、選択条件を作成できます。

- 次の要素は、ビュー定義の選択条件を指定します。

    - [TableControl (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [ListControl (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [WideControl (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [カスタム コントロール (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- 次の要素の選択範囲を指定する共通の条件とビューの定義を制御します。

    - [構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- 次の要素は、コレクション オブジェクトの拡張の選択条件を指定します。

    - [EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- 次の要素は、データの新しいグループを表示するための選択条件を指定します。

    - [GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- 次の要素では、リスト ビューの項目の選択条件を指定します。

    - [ItemSelectionCondition ListControl (形式) を ListItem 要素](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- 次の要素では、コントロールの項目の選択条件を指定します。

    - [ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [コントロールが表示されます (形式) の ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [カスタム コントロール (形式) の ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
