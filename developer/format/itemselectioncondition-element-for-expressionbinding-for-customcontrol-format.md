---
title: カスタム コントロール (形式) の ExpressionBinding ItemSelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858188"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)

このコントロールを使用するのに必要な条件を定義します。 コントロールの項目の指定できる選択条件の数に制限はありません。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem のカスタム コントロールの表示 (形式) の式バインディングのビュー (形式) ItemSelectionCondition 要素のカスタム コントロールのビュー (形式) ExpressionBinding 要素

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
|[ビュー (形式のカスタム コントロールの ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[ビュー (形式) のカスタム コントロールの ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

[ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
