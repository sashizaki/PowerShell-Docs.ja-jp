---
title: View (Format) の CustomControl の ItemSelectionCondition の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b12006-8d52-486b-91a3-e6224ca80e56
caps.latest.revision: 6
ms.openlocfilehash: 52d0b0816eaef6752220e0c3b1249e5a0e44a3ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362441"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、コントロールが使用されます。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for view (format) 式のバインド要素の CustomControl for view (format) の PropertyName Selectioncondition 要素に対する、ItemSelectionCondition の参照 (format) 項目バインドのバインド要素ビューの CustomControl (形式)

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
|[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|このコントロールを使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

条件をトリガーする .NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[CustomControl for ビュー (Format) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
