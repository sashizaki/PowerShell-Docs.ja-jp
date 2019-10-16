---
title: TableControl (Format) の TableRowEntries 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: 88de19be02de4933f892e02093403a82ccdd5788
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368151"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a>TableControl の TableRowEntries 要素 (書式)

テーブルの行を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries 要素 (format)

## <a name="syntax"></a>構文

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TableRowEntries` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl (Format) の TableRowEntries の TableRowEntry 要素](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|必須の要素です。<br /><br /> テーブルの行に表示されるデータを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl 要素 (形式)](./tablecontrol-element-format.md)|ビューのテーブル形式を定義します。|

## <a name="remarks"></a>コメント

テーブルビューには1つ以上の @no__t 0 要素を指定する必要があります。 追加できる @no__t 0 要素の数に上限はありません。また、順序が重要でもありません。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、2つのプロパティの値を表示する行を定義する @no__t 0 要素を示してい[ます。](/dotnet/api/System.Diagnostics.Process)

```xml
<TableRowEntries>
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
</TableRowEntries>

```

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[TableControl 要素 (形式)](./tablecontrol-element-format.md)

[TableRowEntry 要素 (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
