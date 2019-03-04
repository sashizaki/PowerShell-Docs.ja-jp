---
title: ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856188"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a>View の CustomControl の CustomEntry の CustomItem 要素 (書式)

カスタム コントロールのビューで表示するデータと表示方法を定義します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry 表示されます (形式)

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
|[ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[ビュー (形式) のカスタム コントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> カスタム コントロールのビューで表示するデータと表示方法を定義します。|
|[ビュー (形式) 用のカスタム コントロールの CustomItem に改行要素](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールの表示には、空白行を追加します。|
|[CustomItem ビュー (形式) のカスタム コントロールのテキスト要素](./text-element-for-customitem-for-customview-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを追加のテキストを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のカスタム コントロールの CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|カスタム コントロールのビューの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[表示 (形式) CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの CustomItem に改行要素](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[CustomItem ビュー (形式) のカスタム コントロールのテキスト要素](./text-element-for-customitem-for-customview-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
