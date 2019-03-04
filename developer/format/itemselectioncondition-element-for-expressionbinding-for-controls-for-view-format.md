---
title: ExpressionBinding のビュー (形式) のコントロールの要素を ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c15014-2440-410d-b02d-b7f1a49240a0
caps.latest.revision: 7
ms.openlocfilehash: 80f375c53c205c793600655fa6031d114871618e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861848"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)

このコントロールを使用するのに必要な条件を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールコントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素

## <a name="syntax"></a>構文

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
