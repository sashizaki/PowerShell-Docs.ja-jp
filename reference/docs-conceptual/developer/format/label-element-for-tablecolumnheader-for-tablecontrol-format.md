---
title: TableControl (Format) の TableColumnHeader の Label 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365171"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>TableControl の TableColumnHeader の Label 要素 (書式)

列の上部に表示されるラベルを定義します。 この要素は、テーブルビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素の tablecontrol (format) TableColumnHeader 要素の tablecontrol (Format) ラベル要素のTableControl (Format) の TableColumnHeader

## <a name="syntax"></a>構文

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Label` 要素の属性、子要素、および親要素について説明します。 各列に対して使用できるラベルは1つだけです。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableControl の TableHeaders の TableColumnHeader 要素 (Format)](./tablecolumnheader-element-format.md)|テーブルの列のデータのラベル、幅、および配置を定義します。|

## <a name="text-value"></a>テキスト値

テーブルの列の上部に表示されるテキストを指定します。 列ラベルに使用できる文字は制限されていません。

## <a name="remarks"></a>コメント

ラベルが指定されていない場合は、行に表示される値を持つプロパティの名前が使用されます。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

この例は、ラベルが "Column 1" である `TableColumnHeader` 要素を示しています。

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>関連項目

[テーブルビューの作成](./creating-a-table-view.md)

[TableColumnHeader 要素 (Format)](./tablecolumnheader-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
