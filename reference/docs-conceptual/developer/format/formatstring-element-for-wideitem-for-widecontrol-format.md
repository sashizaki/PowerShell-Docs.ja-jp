---
title: WideControl の WideItem の FormatString 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363031"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a>WideControl の WideItem の FormatString 要素 (書式)

プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideEntries Element (format) WideEntry Element for WideItem (format) FormatString 要素の WideControl (Format) WideControl 要素for WideItem for WideControl (Format)

## <a name="syntax"></a>構文

```xml
<FormatString>PropertyPattern</FormatString>
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
|[WideControl の WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)|リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

データの書式設定に使用するパターンを指定します。 たとえば、このパターンを使用すると、型 system.string: {0: MMM} {0: dd} {0: HH}: {0: mm} のプロパティの値を書式設定[できます。](/dotnet/api/System.TimeSpan)

## <a name="remarks"></a>コメント

書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。 ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。

ワイドビューでの書式指定文字列の使用の詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、`StartTime` プロパティの値の書式設定文字列を定義する方法を示しています。

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a>参照

[ワイドビューの作成](./creating-a-wide-view.md)

[WideControl の WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
