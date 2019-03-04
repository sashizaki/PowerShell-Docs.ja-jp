---
title: ScriptBlock 要素の構成 (形式) のコントロールの ItemSeclectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f7aec9-7b01-4370-84f4-1e58508a851f
caps.latest.revision: 6
ms.openlocfilehash: e92b2dfff07358132c480c47c34279e5365fe400
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861858"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の ItemSeclectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素ExpressionBinding ItemSelectionCondition の構成 (形式) のコントロールの構成 (形式) スクリプト ブロックの要素のコントロールの ItemSelectionCondition 要素

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
|[ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|このコントロールを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

指定できないかどうかは、この要素が使用される、 [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)要素の選択条件を定義するときにします。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの ItemSeclectionCondition PropertyName 要素](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
