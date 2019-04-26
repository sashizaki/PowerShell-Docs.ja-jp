---
title: GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065463"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a>GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)

このコントロールを使用するのに必要な条件を定義します。 コントロールの項目の指定できる選択条件の数に制限はありません。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) の GroupBy (形式) ItemSelectionCondition 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール

## <a name="syntax"></a>構文

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[GroupBy (形式) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-groupby-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

[GroupBy (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-groupby-format.md)
