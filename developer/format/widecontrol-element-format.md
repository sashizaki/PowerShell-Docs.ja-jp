---
title: WideControl 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859828"
---
# <a name="widecontrol-element-format"></a>WideControl 要素 (書式)

ワイド (1 つの値) を定義するビューの一覧の形式。 このビューには、1 つのプロパティの値または各オブジェクトのスクリプトの値が表示されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式)

## <a name="syntax"></a>構文

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`WideControl`要素。 指定することはできません、`AutoSize`と`ColumnNumber`同時要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideControl (形式) の AutoSize 要素](./autosize-element-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> かどうか、列のサイズと列の数が調整のデータのサイズを指定します。|
|[ColumnNumber 要素 WideControl (形式)](./columnnumber-element-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> 表示幅が広いに表示される列の数を指定します。|
|[WideEntries 要素 (形式)](./wideentries-element-for-widecontrol-format.md)|必須の要素。<br /><br /> 表示幅が広いの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー要素 (形式)](./view-element-format.md)|1 つまたは複数の .NET オブジェクトを表示するために使用するビューを定義します。|

## <a name="remarks"></a>コメント

ワイド ビューを定義するときに追加できます、`AutoSize`要素、または`ColumnNumber`が、両方を追加することはできません。

ほとんどの場合、1 つだけ定義が必要ですがワイド ビューごとに、同じビューを使用して、さまざまな .NET オブジェクトを表示する場合、複数の定義を指定することができます。 その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。

ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビュー コンポーネント](./creating-a-wide-view.md)します。

## <a name="example"></a>例

次の例は、`WideControl`要素のプロパティを表示するために使用される、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

## <a name="see-also"></a>参照

[WideControl (形式) の Autosize 要素](./autosize-element-for-widecontrol-format.md)

[ColumnNumber 要素 WideControl (形式)](./columnnumber-element-for-widecontrol-format.md)

[ビュー要素 (形式)](./view-element-format.md)

[WideEntries 要素 (形式)](./wideentries-element-for-widecontrol-format.md)

[表示幅が広い (Basic)](./wide-view-basic.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
