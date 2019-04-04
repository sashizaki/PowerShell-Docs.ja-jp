---
title: WideControl (形式) の要素を WideItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862628"
---
# <a name="wideitem-element-for-widecontrol-format"></a>WideControl の WideItem 要素 (書式)

プロパティまたは値が表示されているスクリプトを定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) WideItem 要素 (形式)

## <a name="syntax"></a>構文

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`WideItem`要素。 `FormatString` 要素は省略できます。 ただし、指定する必要があります、`PropertyName`または`ScriptBlock`が、要素は両方で指定できません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideItem WideControl (形式) 用の FormatString 要素](./formatstring-element-for-wideitem-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。|
|[WideItem (形式) の PropertyName 要素](./propertyname-element-for-wideitem-for-widecontrol-format.md)|表示幅値が表示されるオブジェクトのプロパティを指定します。|
|[WideItem (形式) の ScriptBlock 要素](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|値をワイド ビューで表示するスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideEntry 要素 (形式)](./wideentry-element-for-widecontrol-format.md)|ワイド ビューの定義を提供します。|

## <a name="remarks"></a>コメント

ワイド ビューのコンポーネントに関する詳細については、[表示幅が広い](./creating-a-wide-view.md)を参照してください。

## <a name="example"></a>例

次の例は、 `WideEntry` 、1 つを定義する要素`WideItem`要素。 `WideItem`プロパティまたは値を持つが、ビューで表示されているスクリプト要素を定義します。

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

## <a name="see-also"></a>参照

[WideItem WideControl (形式) 用の FormatString 要素](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[WideItem (形式) の PropertyName 要素](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[WideItem (形式) の ScriptBlock 要素](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[WideEntry 要素 (形式)](./wideentry-element-for-widecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
