---
title: 構成 (形式) のコントロールの CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862938"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Configuration の Controls の CustomEntry の CustomItem 要素 (書式)

どのようなデータが、コントロールによって表示され、表示方法を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素コントロールの構成の CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomItem`要素。 詳細については、「解説」を参照してください。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[構成 (形式) のコントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データを左または右にシフトなど、データを表示する方法を定義します。|
|[コントロールの構成 (形式) の CustomItem の改行要素](./newline-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コントロールの表示には、空白行を追加します。|
|[CustomItem の構成 (形式) のコントロールのテキスト要素](./text-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コントロールの表示には、かっこ、角かっこなどのテキストを追加します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

子要素を指定するときに、`CustomItem`要素、次に留意します。

- 次の順序で子要素を追加する必要があります: `ExpressionBinding`、 `NewLine`、 `Text`、および`Frame`します。

- 指定できるシーケンスの数に上限はありません。

- 各シーケンスの数に上限はありません`ExpressionBinding`要素を使用することができます。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[コントロールの構成 (形式) の CustomItem の改行要素](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[CustomItem の構成 (形式) のコントロールのテキスト要素](./text-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
