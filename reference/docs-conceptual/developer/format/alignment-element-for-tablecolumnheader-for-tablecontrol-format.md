---
title: TableControl (Format) の TableColumnHeader の Alignment 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff85e83a-c9c2-4c37-accc-e6a27c182f3c
caps.latest.revision: 19
ms.openlocfilehash: 16b41535109ca503e679a135f5ba30054e33de5b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364381"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>TableControl の TableColumnHeader の Alignment 要素 (書式)

列ヘッダー内のデータを表示する方法を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (format) TableColumnHeader Element (format) Alignment 要素 (format)

## <a name="syntax"></a>構文

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Alignment` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableColumnHeader 要素 (Format)](./tablecolumnheader-element-format.md)|テーブルの列のデータのラベル、幅、および配置を定義します。|

## <a name="text-value"></a>テキスト値

次のいずれかの値を指定します。 これらの値の大文字と小文字は区別されません。

左揃えこの要素が指定されていない場合は、左側の列に表示されるデータが既定値になります。

右側の列に表示されるデータを右揃えにします。

中央には、列に表示されるデータが中央に配置されます。

## <a name="remarks"></a>コメント

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

この例では、データが左側に揃えられている `TableColumnHeader` 要素を示します。

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
