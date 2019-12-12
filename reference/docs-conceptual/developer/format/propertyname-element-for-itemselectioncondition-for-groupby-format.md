---
title: GroupBy (Format) の ItemSelectionCondition の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 221cbdc2-f794-4f3a-9d40-bfdd8cba1013
caps.latest.revision: 6
ms.openlocfilehash: aae65789cf5572cbcc9251eca802a2d43065e49f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362411"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a>GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、コントロールが使用されます。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (format) 式のバインド要素に対して、groupby (format) PropertyName 要素のオブジェクトのバインドのバインド要素GroupBy の ItemSelectionCondition (形式)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|このコントロールを使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

条件をトリガーする .NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[GroupBy (Format) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[GroupBy (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
