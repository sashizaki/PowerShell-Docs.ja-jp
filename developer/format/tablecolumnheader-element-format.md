---
title: TableColumnHeader 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063811"
---
# <a name="tablecolumnheader-element-format"></a>TableColumnHeader 要素 (書式)

ラベル、列の幅と、テーブルの列のラベルの配置を定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders 要素の要素に TableControl (形式) TableColumnHeader TableHeaders TableControl (形式) 用の

## <a name="syntax"></a>構文

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TableColumnHeader`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[TableControl (形式) の TableColumnHeader label 要素](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 列の上部に表示されるラベルを定義します。 ラベルが指定されていない場合は、行の値を持つが表示されるプロパティの名前が使用されます。|
|[TableControl (形式) の TableColumnHeader 幅要素](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|必須の要素。<br /><br /> (文字) で、列の幅を指定します。|
|[TableControl (形式) の TableColumnHeader の alignment 要素](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 列のラベルを表示する方法を指定します。 配置が指定されていない場合、ラベルを左側に配置します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableHeaders 要素 (形式)](./tableheaders-element-format.md)|テーブル ビューの列を定義します。|

## <a name="remarks"></a>コメント

テーブルの各列のヘッダーを指定します。 列が順番に表示されます、`TableColumnHeader`要素が定義されます。

テーブルには、同じ数の必要があります`TableColumnHeader`要素として`TableRowEntry`要素。 列ヘッダーは、テーブルの上部にあるテキストを表示する方法を定義します。 行のエントリでは、テーブルの行で表示するデータを定義します。

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビュー](./creating-a-table-view.md)します。

## <a name="example"></a>例

次の例では 2 つ`TableColumnHeader`要素。 最初の要素は、左側にあるラベルを配置し、ラベルは"Column 1"が 16 文字の幅を持つ列を定義します。 2 番目の要素は、ラベルが、列の中央に配置し、ラベルは"Column 2"が 10 文字の幅を持つ列を定義します。

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

[TableControl (形式) の TableColumnHeader の alignment 要素](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[テーブル ビューを作成します。](./creating-a-table-view.md)

[TableControl (形式) の TableColumnHeader label 要素](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[TableControl (形式) の TableHeaders 要素](./tableheaders-element-format.md)

[TableControl 要素 (形式) の TableColumnHeader の幅](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
