---
title: 構成用のコントロール用の CustomItem の式のバインド要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363191"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a>Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロール用 CustomItem 要素の構成式のバインド要素 CustomItem の構成 (形式)

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
|[構成用のコントロールの式のバインドの CustomControlName 要素 (形式)](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コモンコントロールまたはビューコントロールの名前を指定します。|
|[構成対象のコントロールの式のバインドの列挙 Atecollection 要素 (形式)](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コレクションの要素がコントロールによって表示されることを指定します。|
|[構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> このコモンコントロールを使用するために必要な条件を定義します。|
|[構成用のコントロールの式のバインドの PropertyName 要素 (Format)](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コモンコントロールによって表示される値を持つ .NET プロパティを指定します。|
|[構成用のコントロールの式のバインドの ScriptBlock 要素 (形式)](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 共通コントロールによって値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[構成のための CustomEntry コントロールの CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[構成のための CustomEntry コントロールの CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
