---
title: TableControl (Format) の TableRowEntry の TableColumnItems 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43684ce-7c3d-4d14-8dbd-061c111ee805
caps.latest.revision: 12
ms.openlocfilehash: d05437aaa9652e7f81d0854d1a746acffe145699
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361811"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a>TableControl の TableRowEntry の TableColumnItems 要素 (書式)

値が行内に表示されるプロパティまたはスクリプトを定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)TableControl (Format) の TableControlEntry の TableColumnItems 要素

## <a name="syntax"></a>構文

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TableColumnItems` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[TableControl (Format) の TableColumnItems の TableColumnItem 要素](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|必須の要素です。<br /><br /> 行の列に値が表示されるプロパティまたはスクリプトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableControl (Format) の TableRowEntries の TableRowEntry 要素](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|テーブルの行に表示されるデータを定義します。|

## <a name="remarks"></a>コメント

行の各列には、`TableColumnItem` 要素が必要です。 最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は[、system.object オブジェクト](/dotnet/api/System.Diagnostics.Process)の3つのプロパティを定義する `TableColumnItems` 要素を示しています。

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a>関連項目

[テーブルビューの作成](./creating-a-table-view.md)

[TableColumnItem 要素 (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[TableRowEntry 要素 (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
