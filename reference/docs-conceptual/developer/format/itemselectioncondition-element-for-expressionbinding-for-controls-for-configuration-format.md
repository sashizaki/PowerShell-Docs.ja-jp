---
title: 構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362921"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a>Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)

このコントロールを使用するために必要な条件を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロール用 CustomItem 要素の構成式のバインド要素 CustomItem の構成 (形式)構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)

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
|[構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[構成用のコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[構成用のコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
