---
title: WideControl (形式) の要素を WideEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853278"
---
# <a name="wideentries-element-for-widecontrol-format"></a>WideControl の WideEntries 要素 (書式)

表示幅が広いの定義を提供します。 表示幅が広いには、1 つまたは複数の定義を指定する必要があります。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式)

## <a name="syntax"></a>構文

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`WideEntries`要素。 少なくとも 1 つの子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideEntry 要素 (形式)](./wideentry-element-for-widecontrol-format.md)|ワイド ビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideControl 要素 (形式)](./widecontrol-element-format.md)|ワイド (1 つの値) を定義するビューの一覧の形式。|

## <a name="remarks"></a>コメント

ワイド ビューは、1 つのプロパティの値または各オブジェクトのスクリプト値を表示する一覧の形式です。 ワイド ビューのコンポーネントに関する詳細については、[ワイド ビュー コンポーネント](./creating-a-wide-view.md)を参照してください。

## <a name="example"></a>例

次の例は、 `WideEntries` 、1 つを定義する要素`WideEntry`要素。 `WideEntry`要素には、1 つが含まれています。`WideItem`ビューに表示されるどのようなプロパティやスクリプトの値を定義する要素。

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

## <a name="see-also"></a>参照

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[WideControl 要素 (形式)](./widecontrol-element-format.md)

[WideEntry 要素 (形式)](./wideentry-element-for-widecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
