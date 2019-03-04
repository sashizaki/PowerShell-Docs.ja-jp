---
title: FormatString 要素 TableControl (形式) の TableColumnItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a150731-d4b4-4d63-8db5-f14d463c8c37
caps.latest.revision: 13
ms.openlocfilehash: b7e1d0adc43254141056a729e1c1cc9699b6ac9b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854328"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a>TableControl の TableColumnItem の FormatString 要素 (書式)

テーブルのプロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) TableColumnItems 要素 (形式) TableColumnItem 要素 (形式)TableColumnItem (形式) の FormatString 要素

## <a name="syntax"></a>構文

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`FormatString`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableColumnItem 要素 (形式)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

データの書式設定に使用されるパターンを指定します。 このパターンを使用して、型の任意のプロパティの値の書式など[System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0:mm}。

## <a name="remarks"></a>コメント

テーブルのビューやリスト ビュー、ワイド ビューは、カスタム ビューを作成するときに、書式指定文字列を使用できます。 ビューに表示される値の書式設定に関する詳細については、次を参照してください。[表示されるデータの書式設定](./formatting-displayed-data.md)します。

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビュー](./creating-a-table-view.md)します。

## <a name="example"></a>例

次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[表示されるデータの書式設定](./formatting-displayed-data.md)

[TableColumnItem 要素 (形式)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
