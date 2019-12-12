---
title: TableControl (Format) の TableRowEntries の TableRowEntry 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18d86af7-7ff9-4968-81be-2caa61937d49
caps.latest.revision: 10
ms.openlocfilehash: 946ffb3fe857503c02b9000238a86775969abbd6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361801"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a>TableControl の TableRowEntries の TableRowEntry 要素 (書式)

テーブルの行に表示されるデータを定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)

## <a name="syntax"></a>構文

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TableRowEntry` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl (Format) の TableRowEntry の EntrySelectedBy 要素](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|必須の要素です。<br /><br /> プロパティ値が行内に表示されるオブジェクトを定義します。|
|[TableControl (Format) の TableRowEntry の TableColumnItems 要素](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|必須の要素です。<br /><br /> 値が表示されるプロパティまたはスクリプトを定義します。|
|[TableControl (Format) の TableRowEntry の Wrap 要素](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 列幅を超えるテキストを次の行に表示するように指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl (Format) の TableRowEntries 要素](./tablerowentries-element-for-tablecontrol-format.md)|テーブルの行を定義します。|

## <a name="remarks"></a>コメント

1つの `TableColumnItems` 要素と1つの `EntrySelectedBy` 要素を指定する必要があります。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、`TableRowEntry` の2つのプロパティの値を表示する行を定義する要素を示してい[ます。](/dotnet/api/System.Diagnostics.Process)

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[TableControl (Format) の TableRowEntry の EntrySelectedBy 要素](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[TableControl (Format) の TableRowEntry の TableColumnItems 要素](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[TableControl (Format) の TableRowEntries 要素](./tablerowentries-element-for-tablecontrol-format.md)

[TableControl (Format) の TableRowEntry の Wrap 要素](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
