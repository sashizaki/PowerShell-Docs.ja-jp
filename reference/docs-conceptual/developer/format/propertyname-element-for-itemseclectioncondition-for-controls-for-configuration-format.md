---
title: 構成用のコントロール (Format) の ItemSeclectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8ab181-c559-492e-a0cf-299e381fdcc3
caps.latest.revision: 6
ms.openlocfilehash: ce25789bdfc2679372ca9e42f99dcc6a30ae2def
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362531"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、コントロールが使用されます。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロール用 CustomItem 要素の構成式のバインド要素 CustomItem の構成 (形式)構成用のコントロール (形式) の ItemSeclectionCondition の構成 (Format) PropertyName 要素の式のバインドの ItemSelectionCondition 要素

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
|[構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|このコントロールを使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

条件をトリガーする .NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[ItemSeclectionCondition の ScriptBlock 要素 (構成用コントロール用) (形式)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
