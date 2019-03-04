---
title: ExpressionBinding のビュー (形式) のカスタム コントロールの要素を CustomControlName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea821e8b-4d65-4263-b7e4-6aeca9f534c2
caps.latest.revision: 9
ms.openlocfilehash: b44ced75bbaac7c0744f347bdc97f87365b8fe39
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860438"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a>View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)

一般的なコントロールまたはビューのコントロールの名前を指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素のビュー (形式) CustomItem CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry CustomItem (形式) の式バインディングの CustomItem (形式) CustomControlName 要素のビュー (形式) ExpressionBinding 要素の要素

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
|[ExpressionBinding 要素 CustomItem (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="text-value"></a>テキスト値

コントロールの名前を指定します。

## <a name="remarks"></a>コメント

書式設定ファイルのすべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。 これらのコントロールの名前は、次の要素によって指定されます。

- [構成 (形式) のコントロールのコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)

- [コントロールが表示されます (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[構成 (形式) のコントロールのコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)

[コントロールが表示されます (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-view-format.md)

[ExpressionBinding 要素 CustomItem (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
