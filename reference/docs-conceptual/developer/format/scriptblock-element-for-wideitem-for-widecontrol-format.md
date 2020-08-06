---
title: WideItem for WideControl (Format) の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: be649d6de0d2dfa6bad14f2d7476cced9cd6cb6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787599"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>WideControl の WideItem の ScriptBlock 要素 (書式)

ワイドビューに値が表示されるスクリプトを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) Element for WideItem (Format)

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)|ワイドビューに表示される値を持つプロパティまたはスクリプトブロックを定義します。|

## <a name="text-value"></a>テキスト値

値が表示されるスクリプトを指定します。

## <a name="remarks"></a>解説

ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

この例では、 `WideItem` ビューに値が表示されるスクリプトを定義する要素を示します。

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>参照

[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)

[ワイド ビューを作成する](./creating-a-wide-view.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
