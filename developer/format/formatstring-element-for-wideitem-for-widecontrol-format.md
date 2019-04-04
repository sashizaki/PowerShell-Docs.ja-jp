---
title: FormatString 要素 WideControl (形式) の WideItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860938"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a>WideControl の WideItem の FormatString 要素 (書式)

ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素の要素に WideControl (形式) WideItem WideControl (形式) FormatString 要素WideItem WideControl (形式) 用の

## <a name="syntax"></a>構文

```xml
<FormatString>PropertyPattern</FormatString>
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
|[WideControl (形式) の WideItem 要素](./wideitem-element-for-widecontrol-format.md)|プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

データの書式設定に使用されるパターンを指定します。 たとえば、このパターンを使用型の任意のプロパティの値の書式[System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0:mm}。

## <a name="remarks"></a>コメント

テーブルのビューやリスト ビュー、ワイド ビューは、カスタム ビューを作成するときに、書式指定文字列を使用できます。 ビューに表示される値の書式設定に関する詳細については、[表示されるデータの書式設定](./formatting-displayed-data.md)を参照してください。

ワイド ビューで書式指定文字列の使用に関する詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。

## <a name="example"></a>例

次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a>参照

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[WideControl (形式) の WideItem 要素](./wideitem-element-for-widecontrol-format.md)

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
