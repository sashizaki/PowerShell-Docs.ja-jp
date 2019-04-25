---
title: GroupBy (形式) の ItemSelectionCondition PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 221cbdc2-f794-4f3a-9d40-bfdd8cba1013
caps.latest.revision: 6
ms.openlocfilehash: aae65789cf5572cbcc9251eca802a2d43065e49f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064766"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a>GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする、.NET プロパティを指定します。 このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) PropertyName 要素の GroupBy (形式) ItemSelectionCondition 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロールGroupBy (形式) の ItemSelectionCondition

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
|[GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|このコントロールを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

条件をトリガーする、.NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)要素の選択条件を定義するときにします。

## <a name="see-also"></a>参照

[GroupBy (形式) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
