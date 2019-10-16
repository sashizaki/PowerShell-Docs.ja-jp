---
title: TableControl (Format) の TableColumnHeader の Width 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94eb0535-8002-4f17-9a2b-4be75ec20e5c
caps.latest.revision: 18
ms.openlocfilehash: 4a25c9d81df670dc10955065bfb66766cdb1bd33
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367871"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>TableControl の TableColumnHeader の Width 要素 (書式)

列の幅 (文字数) を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 TableControl (format) の TableColumnHeader 要素 TableHeaders for TableControl (Format) Width 要素TableControl (Format) の TableColumnHeader

## <a name="syntax"></a>構文

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>属性と要素

以下のセクションでは、列ヘッダーを定義するときに使用される `Width` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl の TableHeaders の TableColumnHeader 要素 (Format)](./tablecolumnheader-element-format.md)|テーブルの列のデータのラベル、幅、および配置を定義します。|

## <a name="text-value"></a>テキスト値

可能な限り、表示されるプロパティ値の長さを超える幅 (文字数) を指定します。

## <a name="remarks"></a>コメント

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、幅が16文字の @no__t 0 要素を示しています。

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[TableControl の TableHeader の TableColumnHeader 要素 (Format)](./tablecolumnheader-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
