---
title: WideControl の WideEntries 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785049"
---
# <a name="wideentries-element-for-widecontrol-format"></a>WideControl の WideEntries 要素 (書式)

ワイドビューの定義を提供します。 ワイドビューでは、1つまたは複数の定義を指定する必要があります。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideEntries 要素 (形式)

## <a name="syntax"></a>構文

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `WideEntries` ます。 少なくとも1つの子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)|ワイドビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideControl 要素 (書式)](./widecontrol-element-format.md)|ビューのワイド (単一値) リスト形式を定義します。|

## <a name="remarks"></a>解説

ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。 ワイドビューのコンポーネントの詳細については、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、 `WideEntries` 1 つの要素を定義する要素を示して `WideEntry` います。 要素には、 `WideEntry` `WideItem` ビューに表示されるプロパティまたはスクリプトの値を定義する1つの要素が含まれます。

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。

## <a name="see-also"></a>参照

[ワイド ビューを作成する](./creating-a-wide-view.md)

[WideControl 要素 (書式)](./widecontrol-element-format.md)

[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
