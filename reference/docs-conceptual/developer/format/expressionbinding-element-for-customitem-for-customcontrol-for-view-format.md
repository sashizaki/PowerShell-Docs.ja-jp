---
title: CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363151"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for ビュー (形式) の Custommentry 要素の CustomControl for View (Format) CustomEntry for CustomControl の CustomItem 要素 for view (Format) CustomControl for View (format) の CustomItem のバインド要素

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

次のセクションでは、`ExpressionBinding` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|`CustomControl Element`|省略可能な要素です。<br /><br /> このコントロールによって使用されるコントロールを定義します。|
|[CustomControl for View (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コモンコントロールまたはビューコントロールの名前を指定します。|
|[CustomControl for View (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コレクションの要素が表示されることを指定します。|
|[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|省略可能な要素です。<br /><br /> このコントロールを使用するために必要な条件を定義します。|
|[CustomControl for View (Format) の式のバインドの PropertyName 要素](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示される値を持つ .NET プロパティを指定します。|
|[CustomCustomControl for View (Format) の式のバインドの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomEntry for CustomControl の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[CustomControl for View (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[CustomControl for View (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[CustomControl for View (Format) の式のバインドの PropertyName 要素](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[CustomControl for View (Format) の式のバインドの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[CustomEntry for CustomControl の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
