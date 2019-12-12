---
title: CustomControl (Format) の式のバインドの ItemSelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362911"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)

このコントロールを使用するために必要な条件を定義します。 コントロール項目に指定できる選択条件の数に制限はありません。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for View (Format) の式バインドの CustomControl for view (format) ItemSelectionCondition 要素のための CustomEntry for view (format) 式のバインド要素

## <a name="syntax"></a>構文

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ItemSelectionCondition` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[ビューの CustomControl の ItemSelectionCondition の PropertyName 要素 (形式)](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[CustomControl for ビュー (Format) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

[CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
