---
title: ビュー (Format) のコントロールに対する CustomEntry の CustomItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363941"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>View の Controls の CustomEntry の CustomItem 要素 (書式)

コントロールによって表示されるデータとその表示方法を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (Format) CustomEntry 要素を使用して、ビュー (形式) のコントロールのためのビュー (形式) Customentries 要素を表示します。

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomItem` 要素の属性、子要素、および親要素について説明します。 詳細については、「解説」を参照してください。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ビューのコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[ビューのコントロールの CustomItem の Frame 要素 (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> データを左右に移動するなど、データの表示方法を定義します。|
|[ビューのコントロールの CustomItem の改行要素 (Format)](./newline-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールの表示に空白行を追加します。|
|[ビューのコントロールの CustomItem のテキスト要素 (書式)](./text-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> かっこや角かっこなどのテキストをコントロールの表示に追加します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビューのコントロール (Format) の CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

`CustomItem` 要素の子要素を指定する場合は、次の点に注意してください。

- 子要素は、`ExpressionBinding`、`NewLine`、`Text`、および `Frame`の順に追加する必要があります。

- 指定できるシーケンスの数に上限はありません。

- 各シーケンスには、使用できる `ExpressionBinding` 要素の数に上限はありません。

## <a name="see-also"></a>関連項目

[ビューのコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[ビューのコントロールの CustomItem の Frame 要素 (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)

[ビューのコントロールの CustomItem の改行要素 (Format)](./newline-element-for-customitem-for-controls-for-view-format.md)

[ビューのコントロールの CustomItem のテキスト要素 (書式)](./text-element-for-customitem-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
