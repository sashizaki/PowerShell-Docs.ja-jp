---
title: PropertyName WideItem WideControl (形式) の要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860958"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a>WideControl の WideItem の PropertyName 要素 (書式)

表示幅値が表示されるオブジェクトのプロパティを指定します。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) WideItem 要素 (形式) PropertyName の構成要素 WideItem (形式)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)|プロパティまたは値を持つがワイド ビューで表示されているスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

値が表示されるプロパティの名前を指定します。

## <a name="remarks"></a>コメント

ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。

## <a name="example"></a>例

この例の ProcessName プロパティの値を表示するワイド ビューを示して、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a>参照

[WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
