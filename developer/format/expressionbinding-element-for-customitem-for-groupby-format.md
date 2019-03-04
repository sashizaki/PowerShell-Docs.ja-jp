---
title: GroupBy (形式) の CustomItem ExpressionBinding 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854928"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a>GroupBy の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール

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

次のセクションでは、属性、子要素、およびの親要素について説明します、`ExpressionBinding`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|`CustomControl Element`|省略可能な要素です。<br /><br /> このコントロールで使用されるコントロールを定義します。|
|[GroupBy (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素です。<br /><br /> 一般的なコントロールまたはビューのコントロールの名前を指定します。|
|[GroupBy (形式) の ExpressionBinding EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (形式) の ExpressionBinding EnumerateCollection 要素|省略可能な要素です。<br /><br /> コレクションの要素が表示されることを指定します。|
|[GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素です。<br /><br /> このコントロールを使用するのに必要な条件を定義します。|
|[GroupBy (形式) の ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素です。<br /><br /> 値を持つが、コントロールによって表示される、.NET プロパティを指定します。|
|[GroupBy (形式) の ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|省略可能な要素です。<br /><br /> 値を持つが、コントロールによって表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-groupby-format.md)|カスタム コントロールのビューで表示するデータと表示方法を定義します。|

## <a name="see-also"></a>参照

[GroupBy (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (形式) の ExpressionBinding EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (形式) の ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (形式) の ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
