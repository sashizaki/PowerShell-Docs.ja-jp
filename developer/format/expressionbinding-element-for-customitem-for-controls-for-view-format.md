---
title: ExpressionBinding 要素のビュー (形式) のコントロールの CustomItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065951"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>View の Controls の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ExpressionBinding`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|`CustomControl Element`|省略可能な要素です。<br /><br /> このコントロールで使用されるコントロールを定義します。|
|[コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 一般的なコントロールまたはビューのコントロールの名前を指定します。|
|[コントロールが表示されます (形式) の ExpressionBinding EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コレクションの要素が表示されることを指定します。|
|[コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロールを使用するのに必要な条件を定義します。|
|[コントロールが表示されます (形式) の ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 値を持つが、コントロールによって表示される、.NET プロパティを指定します。|
|[コントロールが表示されます (形式) の ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 値を持つが、コントロールによって表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-view-format.md)|どのようなデータが、コントロールによって表示され、表示方法を定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ExpressionBinding EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
