---
title: GroupBy (Format) の CustomItem の式のバインド要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368631"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a>GroupBy の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の CustomItem 要素には、GroupBy (format) の CustomItem のバインド要素が指定しています。

## <a name="syntax"></a>構文

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`ExpressionBinding` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|`CustomControl Element`|省略可能な要素。<br /><br /> このコントロールによって使用されるコントロールを定義します。|
|[GroupBy (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素。<br /><br /> コモンコントロールまたはビューコントロールの名前を指定します。|
|[GroupBy (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (Format) の式のバインドの列挙 Atecollection 要素|省略可能な要素。<br /><br /> コレクションの要素が表示されることを指定します。|
|[GroupBy (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素。<br /><br /> このコントロールを使用するために必要な条件を定義します。|
|[GroupBy (Format) の式のバインドの PropertyName 要素](./propertyname-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素。<br /><br /> コントロールによって表示される値を持つ .NET プロパティを指定します。|
|[GroupBy (Format) の式のバインドの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素。<br /><br /> コントロールによって値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy の CustomEntry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-groupby-format.md)|カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|

## <a name="see-also"></a>参照

[GroupBy (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (Format) の式のバインドの PropertyName 要素](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (Format) の式のバインドの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[GroupBy の CustomEntry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
