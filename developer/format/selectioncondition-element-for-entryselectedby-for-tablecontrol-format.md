---
title: TableControl (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861238"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a>TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)

テーブル ビューのこの定義に使用する必要があります条件を定義します。 テーブルの定義に指定できる選択条件の数に制限はありません。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素を TableRowEntry (形式)TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素

## <a name="syntax"></a>構文

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、および SelectionCondition 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[SelectionCondition EntrySelectedBy TableRowEntry (形式) のための PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[SelectionCondition EntrySelectedBy TableRowEntry (形式) のためのスクリプト ブロックの要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableRowEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|このテーブルのエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。|

## <a name="remarks"></a>コメント

リストの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。

選択条件を定義している場合は、次の要件が適用されます。

- 選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。

選択条件を使用する方法の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[SelectionCondition EntrySelectedBy TableRowEntry (形式) のための PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[SelectionCondition EntrySelectedBy TableRowEntry (形式) のためのスクリプト ブロックの要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
