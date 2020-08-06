---
title: TableControl (Format) の TableColumnHeader の Alignment 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1bf395b84af90d725c14b2f0ef569f72b5fcc613
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783927"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>TableControl の TableColumnHeader の Alignment 要素 (書式)

列ヘッダー内のデータを表示する方法を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (format) TableColumnHeader Element (format) Alignment 要素 (format)

## <a name="syntax"></a>構文

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `Alignment` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableColumnHeader 要素 (書式)](./tablecolumnheader-element-format.md)|テーブルの列のデータのラベル、幅、および配置を定義します。|

## <a name="text-value"></a>テキスト値

次のいずれかの値を指定します。 これらの値では大文字と小文字が区別されません。

左揃えこの要素が指定されていない場合は、左側の列に表示されるデータが既定値になります。

右側の列に表示されるデータを右揃えにします。

中央には、列に表示されるデータが中央に配置されます。

## <a name="remarks"></a>解説

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

この例では、 `TableColumnHeader` データが左側に揃えられている要素を示します。

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>参照

[テーブル ビューを作成する](./creating-a-table-view.md)

[TableColumnHeader 要素 (書式)](./tablecolumnheader-element-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
