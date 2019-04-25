---
title: コントロールが表示されます (形式) の CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066382"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>View の Controls の CustomEntry の CustomItem 要素 (書式)

どのようなデータが、コントロールによって表示され、表示方法を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry ビュー (形式) のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomItem`要素。 詳細については、「解説」を参照してください。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[コントロールが表示されます (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> データを左または右にシフトなど、データを表示する方法を定義します。|
|[コントロールが表示されます (形式) の CustomItem の改行要素](./newline-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールの表示には、空白行を追加します。|
|[CustomItem ビュー (形式) のコントロールのテキスト要素](./text-element-for-customitem-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールの表示には、かっこ、角かっこなどのテキストを追加します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

子要素を指定するときに、`CustomItem`要素、次に留意します。

- 次の順序で子要素を追加する必要があります: `ExpressionBinding`、 `NewLine`、 `Text`、および`Frame`します。

- 指定できるシーケンスの数に上限はありません。

- 各シーケンスの数に上限はありません`ExpressionBinding`要素を使用することができます。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomItem の改行要素](./newline-element-for-customitem-for-controls-for-view-format.md)

[CustomItem ビュー (形式) のコントロールのテキスト要素](./text-element-for-customitem-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
