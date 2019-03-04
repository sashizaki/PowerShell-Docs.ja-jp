---
title: ExpressionBinding の構成 (形式) のコントロールの要素を ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861688"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a>Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)

このコントロールを使用するのに必要な条件を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素

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
|[構成 (形式) のコントロールの ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[構成 (形式) のコントロールの ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの ItemSelectionCondition PropertyName 要素](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
