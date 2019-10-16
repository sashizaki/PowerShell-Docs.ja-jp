---
title: TableColumnHeader 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361851"
---
# <a name="tablecolumnheader-element-format"></a>TableColumnHeader 要素 (書式)

ラベル、列の幅、およびテーブルの列のラベルの配置を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 tablecontrol (format) の TableHeaders の TableColumnHeader 要素 (Format)

## <a name="syntax"></a>構文

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`TableColumnHeader` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl (Format) の TableColumnHeader の Label 要素](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 列の上部に表示されるラベルを定義します。 ラベルが指定されていない場合は、行に表示される値を持つプロパティの名前が使用されます。|
|[TableControl の TableColumnHeader の Width 要素 (Format)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|必須の要素です。<br /><br /> 列の幅 (文字数) を指定します。|
|[TableControl (Format) の TableColumnHeader の Alignment 要素](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 列のラベルを表示する方法を指定します。 アラインメントが指定されていない場合、ラベルは左揃えで配置されます。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableHeaders 要素 (書式)](./tableheaders-element-format.md)|テーブルビューの列を定義します。|

## <a name="remarks"></a>コメント

テーブルの列ごとにヘッダーを指定します。 列は、@no__t 0 の要素が定義されている順序で表示されます。

テーブルには、`TableRowEntry` 要素と同じ数の @no__t 0 要素が必要です。 列ヘッダーは、テーブルの上部のテキストの表示方法を定義します。 行のエントリによって、テーブルの行に表示されるデータが定義されます。

テーブルビューのコンポーネントの詳細については、「[テーブルビュー](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、2つの @no__t 0 要素を示しています。 最初の要素は、ラベルが "Column 1" で、幅が16文字で、ラベルが左揃えである列を定義します。 2番目の要素は、ラベルが "Column 2" で、幅が10文字で、列のラベルが中央にある列を定義します。

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
    <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a>参照

[TableControl (Format) の TableColumnHeader の Alignment 要素](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[テーブルビューの作成](./creating-a-table-view.md)

[TableControl (Format) の TableColumnHeader の Label 要素](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[TableControl の TableHeaders 要素 (Format)](./tableheaders-element-format.md)

[TableColumnHeader for TableControl 要素の幅 (形式)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
