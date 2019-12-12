---
title: GroupBy (Format) の式のバインドの ItemSelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365291"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a>GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)

このコントロールを使用するために必要な条件を定義します。 コントロール項目に指定できる選択条件の数に制限はありません。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (形式) の式のバインド要素 groupby (format) ItemSelectionCondition 要素に対して groupby (形式) の式のバインドのバインド要素

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
|[GroupBy (Format) の ItemSelectionCondition の PropertyName 要素](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[GroupBy (Format) の ItemSelectionCondition の ScriptBlock 要素](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-groupby-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

[GroupBy (Format) の CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-groupby-format.md)
