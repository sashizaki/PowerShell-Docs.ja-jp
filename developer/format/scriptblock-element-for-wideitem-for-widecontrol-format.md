---
title: WideItem WideControl (形式) 用のスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858028"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>WideControl の WideItem の ScriptBlock 要素 (書式)

値をワイド ビューで表示するスクリプトを指定します。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) WideItem 要素 (形式) スクリプト ブロックの構成要素 WideItem (形式)

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)|表示幅値が表示されるプロパティまたはスクリプト ブロックを定義します。|

## <a name="text-value"></a>テキスト値

値が表示されているスクリプトを指定します。

## <a name="remarks"></a>コメント

ワイド ビューのコンポーネントに関する詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。

## <a name="example"></a>例

この例では、`WideItem`値を持つが、ビューに表示するスクリプトを定義する要素。

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>参照

[WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
