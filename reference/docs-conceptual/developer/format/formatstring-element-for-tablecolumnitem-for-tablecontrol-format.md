---
title: TableControl (Format) の TableColumnItem の FormatString 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a150731-d4b4-4d63-8db5-f14d463c8c37
caps.latest.revision: 13
ms.openlocfilehash: b7e1d0adc43254141056a729e1c1cc9699b6ac9b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363711"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a>TableControl の TableColumnItem の FormatString 要素 (書式)

テーブルのプロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (Format)TableColumnItem の FormatString 要素 (Format)

## <a name="syntax"></a>構文

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`FormatString` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableColumnItem 要素 (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|行の列に値が表示されるプロパティまたはスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

データの書式設定に使用するパターンを指定します。 たとえば、このパターンを使用して、型が system.string のプロパティの値を書式設定することができ[ます。 Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0: dd} {0: HH}: {0: mm}。

## <a name="remarks"></a>コメント

書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。 ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。

テーブルビューのコンポーネントの詳細については、「[テーブルビュー](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、`StartTime` プロパティの値の書式設定文字列を定義する方法を示しています。

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[表示データの書式設定](./formatting-displayed-data.md)

[TableColumnItem 要素 (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
