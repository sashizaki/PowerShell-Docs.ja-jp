---
title: TableHeaders 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856878"
---
# <a name="tableheaders-element-format"></a>TableHeaders 要素 (Format)

テーブルの列のヘッダーを定義します。

TableControl (形式) の表示要素 (形式) TableControl 要素 (形式) の TableHeaders 要素 ViewDefinitions 要素 (形式)

## <a name="syntax"></a>構文

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TableHeaders`要素。 各プロパティが表示されるオブジェクトの子要素があります。 列のヘッダー情報は、子要素が指定されている順序で表示されます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[TableColumnHeader 要素 (形式)](./tablecolumnheader-element-format.md)|省略可能な要素です。<br /><br /> ラベル、幅、およびテーブル ビューの列のデータの配置を定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableControl 要素 (形式)](./tablecontrol-element-format.md)|ビューのテーブル形式を定義します。|

## <a name="remarks"></a>コメント

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="example"></a>例

この例では、 `TableHeaders` 2 つの列ヘッダーを定義する要素。

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

[テーブル ビューを作成します。](./creating-a-table-view.md)

[TableColumnHeader 要素 (形式)](./tablecolumnheader-element-format.md)

[TableControl 要素 (形式)](./tablecontrol-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
