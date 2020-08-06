---
title: 構成用のコントロール (Format) の ItemSeclectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f44b1a7f059fa5f41c19eed93762b61eda5110e8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772894"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の ItemSeclectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトがに評価されると、 `true` 条件が満たされ、コントロールが使用されます。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロールの要素の構成 (書式) の CustomControl の構成 (形式) の CustomEntries 要素の構成のためのコントロールの CustomControl のための構成 (形式) CustomEntry コントロールのための構成式のバインド要素の構成式のバインド要素の構成のためのコントロールの構成 (形式) ItemSelectionCondition 要素のコントロールに対するコントロールの構成 (format) ScriptBlock 要素の構成用のコントロールの ItemSelectionCondition の要素のバインドの構成 (形式)

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|このコントロールを使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>解説

この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
