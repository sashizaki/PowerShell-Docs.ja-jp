---
title: TableControl (Format) の TableRowEntry の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363341"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a>TableControl の TableRowEntry の EntrySelectedBy 要素 (書式)

テーブルビューのこの定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) 要素 (format) のエントリ

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`EntrySelectedBy` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl の EntrySelectedBy の SelectionCondition 要素 (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> このテーブルビュー定義を使用するために必要な条件を定義します。|
|[TableControl (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> このテーブルビュー定義を使用する一連の .NET 型を指定します。|
|[TableControl の EntrySelectedBy の TypeName 要素 (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> このテーブルビュー定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl (Format) の TableRowEntry 要素](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|テーブルの行に表示されるデータを定義します。|

## <a name="remarks"></a>コメント

テーブルビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true` に評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用されます。 選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、@no__t 0 の要素を示しています。この要素は[、system.object オブジェクト](/dotnet/api/System.Diagnostics.Process)のプロパティを表示するために使用されます。

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[TableControl の EntrySelectedBy の SelectionCondition 要素 (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[TableControl (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[TableControl (Format) の TableRowEntry 要素](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[TableControl の EntrySelectedBy の TypeName 要素 (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
