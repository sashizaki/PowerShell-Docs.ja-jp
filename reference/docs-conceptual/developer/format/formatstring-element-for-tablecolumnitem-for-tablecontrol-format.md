---
title: TableControl (Format) の TableColumnItem の FormatString 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 848583e697d0ab7bd5b017c14c47aba3c51a3c17
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781547"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a>TableControl の TableColumnItem の FormatString 要素 (書式)

テーブルのプロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (format) TableColumnItem (format) の FormatString 要素

## <a name="syntax"></a>構文

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `FormatString` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableColumnItem 要素 (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|行の列に値が表示されるプロパティまたはスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

データの書式設定に使用するパターンを指定します。 たとえば、このパターンを使用して、型が system.string のプロパティの値を書式設定することができ[ます。 Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0: dd} {0: HH}: {0: mm}。

## <a name="remarks"></a>解説

書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。 ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。

テーブルビューのコンポーネントの詳細については、「[テーブルビュー](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、プロパティの値の書式設定文字列を定義する方法を示して `StartTime` います。

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a>参照

[テーブル ビューを作成する](./creating-a-table-view.md)

[表示されるデータの書式を設定する](./formatting-displayed-data.md)

[TableColumnItem 要素 (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
