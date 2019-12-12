---
title: ビューのコントロールに対する CustomItem の式のバインド要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363781"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>View の Controls の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (形式) のコントロールに対する Customentries のビュー (形式) 式のバインド要素のビュー (形式) の Customentries 要素のコントロールの CustomEntries に対して、ビュー (形式) 用に設定します。

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
|[ビューのコントロール (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コモンコントロールまたはビューコントロールの名前を指定します。|
|[ビューのコントロール (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コレクションの要素を表示することを指定します。|
|[ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロールを使用するために必要な条件を定義します。|
|[ビューのコントロール (Format) の式のバインドの PropertyName 要素](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示される値を持つ .NET プロパティを指定します。|
|[ビューのコントロール (Format) の式のバインドの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-controls-for-view-format.md)|コントロールによって表示されるデータとその表示方法を定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[ビューのコントロール (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[ビューのコントロール (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[ビューのコントロール (Format) の式のバインドの PropertyName 要素](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[ビューのコントロール (Format) の式のバインドの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
