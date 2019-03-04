---
title: コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4191157-bf01-4831-b221-6f8cc581cd53
caps.latest.revision: 6
ms.openlocfilehash: 0cbefbb48427b56d4ae2a5ae27c7726dcfad7b84
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856738"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a>View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールExpressionBinding ItemSelectionCondition ビュー (形式) のコントロールのビュー (形式) スクリプト ブロックの要素のコントロールの ItemSelectionCondition 要素

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
|[コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|このコントロールを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

指定できないかどうかは、この要素が使用される、 [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)要素の選択条件を定義するときにします。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
