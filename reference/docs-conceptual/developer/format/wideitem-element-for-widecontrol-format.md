---
title: WideControl の WideItem 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361401"
---
# <a name="wideitem-element-for-widecontrol-format"></a>WideControl の WideItem 要素 (書式)

値が表示されるプロパティまたはスクリプトを定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (Format) WideEntries Element (format) WideEntry Element (format) WideItem Element (Format)

## <a name="syntax"></a>構文

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`WideItem` 要素の属性、子要素、および親要素について説明します。 `FormatString` 要素は省略可能です。 ただし、`PropertyName` または `ScriptBlock` 要素を指定する必要がありますが、両方を指定することはできません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideControl の WideItem の FormatString 要素 (形式)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。|
|[WideItem の PropertyName 要素 (形式)](./propertyname-element-for-wideitem-for-widecontrol-format.md)|ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。|
|[WideItem の ScriptBlock 要素 (形式)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|ワイドビューに値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)|ワイドビューの定義を提供します。|

## <a name="remarks"></a>コメント

ワイドビューのコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、単一の `WideItem` 要素を定義する `WideEntry` 要素を示しています。 `WideItem` 要素は、ビューに値が表示されるプロパティまたはスクリプトを定義します。

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。

## <a name="see-also"></a>関連項目

[WideControl の WideItem の FormatString 要素 (形式)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[WideItem の PropertyName 要素 (形式)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[WideItem の ScriptBlock 要素 (形式)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
