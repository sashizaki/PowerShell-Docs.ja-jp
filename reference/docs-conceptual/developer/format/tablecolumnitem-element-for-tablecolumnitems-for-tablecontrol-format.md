---
title: TableControl (Format) の TableColumnItems の TableColumnItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 9e6cffc7476ef01124d95ecbf287d9788b0324c9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368231"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>TableControl の TableColumnItems の TableColumnItem 要素 (書式)

行の列に値が表示されるプロパティまたはスクリプトを定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)TableColumnItems for TableControl (Format) の TableControlEntry の TableColumnItems 要素 (Format) TableColumnItem 要素

## <a name="syntax"></a>構文

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TableColumnItem` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl (Format) の TableColumnItem の Alignment 要素](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 行の列のデータをどのように表示するかを定義します。|
|[TableControl (Format) の TableColumnItem の FormatString 要素](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|行の列のデータの書式設定に使用する形式パターンを指定します。|
|[TableControl (Format) の TableColumnItem の PropertyName 要素](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 値が表示されるプロパティの名前を指定します。|
|[TableControl (Format) の TableColumnItem の ScriptBlock 要素](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 行の列に値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl (Format) の TableControlEntry の TableColumnItems 要素](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|値が行内に表示されるプロパティまたはスクリプトを定義します。|

## <a name="remarks"></a>コメント

行の各列に、オブジェクトまたはスクリプトのプロパティを指定できます。 子要素が指定されていない場合、項目はプレースホルダーであり、データは表示されません。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

この例は、@no__t 0 の要素を示しています。この要素は[、system.object オブジェクト](/dotnet/api/System.Diagnostics.Process)の `Status` プロパティの値を表示します。

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[TableControl (Format) の TableColumnItem の Alignment 要素](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[TableColumnItems 要素 (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[TableControl (Format) の TableColumnItem の FormatString 要素](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[TableControl (Format) の TableColumnItem の PropertyName 要素](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[TableControl (Format) の TableColumnItem の ScriptBlock 要素](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
