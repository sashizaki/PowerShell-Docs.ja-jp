---
title: WideControl の WideEntries 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361431"
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

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`WideEntries` 要素の属性、子要素、および親要素について説明します。 少なくとも1つの子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)|ワイドビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideControl 要素 (Format)](./widecontrol-element-format.md)|ビューのワイド (単一値) リスト形式を定義します。|

## <a name="remarks"></a>コメント

ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。 ワイドビューのコンポーネントの詳細については、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、単一の `WideEntry` 要素を定義する `WideEntries` 要素を示しています。 `WideEntry` 要素には、ビューに表示されるプロパティまたはスクリプトの値を定義する1つの `WideItem` 要素が含まれています。

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

## <a name="see-also"></a>関連項目

[ワイドビューの作成](./creating-a-wide-view.md)

[WideControl 要素 (Format)](./widecontrol-element-format.md)

[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
