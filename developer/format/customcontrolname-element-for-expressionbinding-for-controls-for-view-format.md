---
title: ExpressionBinding のビュー (形式) のコントロールの要素を CustomControlName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b6ee11e-9086-41d2-afd3-42fb9f24da69
caps.latest.revision: 7
ms.openlocfilehash: bf1d57447f9018f1535af14466427aaeabc048f3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855598"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a>View の Controls の ExpressionBinding の CustomControlName 要素 (書式)

一般的なコントロールまたはビューのコントロールの名前を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) CustomControlName のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールコントロールが表示されます (形式) の ExpressionBindine 要素

## <a name="syntax"></a>構文

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="text-value"></a>テキスト値

コントロールの名前を指定します。

## <a name="remarks"></a>コメント

書式設定ファイルでは、すべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。 次の要素は、これらのコントロールの名前を指定します。

- [構成 (形式) のコントロールのコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)

- [コントロールが表示されます (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[構成 (形式) のコントロールのコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)

[コントロールが表示されます (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
