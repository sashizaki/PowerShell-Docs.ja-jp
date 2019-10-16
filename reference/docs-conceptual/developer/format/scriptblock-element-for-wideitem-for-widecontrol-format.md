---
title: WideItem for WideControl (Format) の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362031"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>WideControl の WideItem の ScriptBlock 要素 (書式)

ワイドビューに値が表示されるスクリプトを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) Element for WideItem (Format)

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)|ワイドビューに表示される値を持つプロパティまたはスクリプトブロックを定義します。|

## <a name="text-value"></a>テキスト値

値が表示されるスクリプトを指定します。

## <a name="remarks"></a>コメント

ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

この例は、値がビューに表示されるスクリプトを定義する @no__t 0 の要素を示しています。

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>参照

[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
