---
title: ScriptBlock 要素のビュー (形式) のカスタム コントロールの ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 946cd2b5-ac37-4a13-bb49-29fbc70ec8d7
caps.latest.revision: 6
ms.openlocfilehash: 0c07ab0e5d04c4056a7e7215bfa55773bfccb41d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862238"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem の ItemSelectionCondition のビュー (形式) スクリプト ブロックの要素のカスタム コントロールの式バインディングのビュー (形式) ItemSelectionCondition 要素のカスタム コントロール用のビュー (形式) ExpressionBinding 要素カスタム コントロールのビュー (形式)

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|このコントロールを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

指定できないかどうかは、この要素が使用される、 [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素の選択条件を定義するときにします。

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールの ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
