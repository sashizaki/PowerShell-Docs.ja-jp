---
title: GroupBy (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363881"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>GroupBy の CustomEntry の CustomItem 要素 (書式)

カスタムコントロールビューとその表示方法によって表示されるデータを定義します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素の groupby (format) CustomControl 要素の groupby (書式) Customentries 要素の CustomControl の CustomEntries 要素GroupBy の CustomEntry (形式)

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomItem` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[GroupBy (Format) の CustomItem の Frame 要素](./frame-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|
|[GroupBy (Format) の CustomItem の改行要素](./newline-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールの表示に空白行を追加します。|
|[GroupBy (Format) の CustomItem のテキスト要素](./text-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータに追加のテキストを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomControl の CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)|カスタムコントロールビューの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[GroupBy (Format) の CustomControl の CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)

[GroupBy (Format) の CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-groupby-format.md)

[GroupBy (Format) の CustomItem の Frame 要素](./frame-element-for-customitem-for-groupby-format.md)

[GroupBy (Format) の CustomItem の改行要素](./newline-element-for-customitem-for-groupby-format.md)

[GroupBy (Format) の CustomItem のテキスト要素](./text-element-for-customitem-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
