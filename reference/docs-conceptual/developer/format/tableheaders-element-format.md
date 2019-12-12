---
title: TableHeaders 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361821"
---
# <a name="tableheaders-element-format"></a>TableHeaders 要素 (Format)

テーブルの列のヘッダーを定義します。

ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (Format)

## <a name="syntax"></a>構文

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TableHeaders` 要素の属性、子要素、および親要素について説明します。 表示されるオブジェクトの各プロパティには、子要素が必要です。 列ヘッダー情報は、子要素が指定されている順序で表示されます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableColumnHeader 要素 (Format)](./tablecolumnheader-element-format.md)|省略可能な要素です。<br /><br /> テーブルビューの列のデータのラベル、幅、および配置を定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl 要素 (形式)](./tablecontrol-element-format.md)|ビューのテーブル形式を定義します。|

## <a name="remarks"></a>コメント

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、2つの列ヘッダーを定義する `TableHeaders` 要素を示しています。

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

[テーブルビューの作成](./creating-a-table-view.md)

[TableColumnHeader 要素 (Format)](./tablecolumnheader-element-format.md)

[TableControl 要素 (形式)](./tablecontrol-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
