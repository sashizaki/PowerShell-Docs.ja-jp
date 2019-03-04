---
title: GroupBy (形式) の CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856928"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>GroupBy の CustomEntry の CustomItem 要素 (書式)

カスタム コントロールのビューで表示するデータと表示方法を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomItem 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の CustomEntry

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

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomItem`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[GroupBy (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> カスタム コントロールのビューで表示するデータと表示方法を定義します。|
|[GroupBy (形式) の CustomItem に改行要素](./newline-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールの表示には、空白行を追加します。|
|[CustomItem GroupBy (形式) 用のテキスト要素](./text-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを追加のテキストを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) のカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)|カスタム コントロールのビューの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[GroupBy (形式) のカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)

[GroupBy (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-groupby-format.md)

[GroupBy (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-groupby-format.md)

[GroupBy (形式) の CustomItem に改行要素](./newline-element-for-customitem-for-groupby-format.md)

[CustomItem GroupBy (形式) 用のテキスト要素](./text-element-for-customitem-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
