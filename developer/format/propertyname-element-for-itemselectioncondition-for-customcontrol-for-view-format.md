---
title: PropertyName 要素のビュー (形式) のカスタム コントロールの ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b12006-8d52-486b-91a3-e6224ca80e56
caps.latest.revision: 6
ms.openlocfilehash: 52d0b0816eaef6752220e0c3b1249e5a0e44a3ee
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064868"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする、.NET プロパティを指定します。 このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem の ItemSelectionCondition のビュー (形式) PropertyName 要素のカスタム コントロールの式バインディングのビュー (形式) ItemSelectionCondition 要素のカスタム コントロール用のビュー (形式) ExpressionBinding 要素ビュー (形式のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|このコントロールを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

条件をトリガーする、.NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素の選択条件を定義するときにします。

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールの ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
