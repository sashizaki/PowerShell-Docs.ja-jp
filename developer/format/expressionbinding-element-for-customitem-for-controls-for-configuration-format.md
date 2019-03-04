---
title: ExpressionBinding 要素の構成 (形式) のコントロールの CustomItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855138"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a>Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素

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
|[ExpressionBinding の構成 (形式) のコントロールの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 一般的なコントロールまたはビューのコントロールの名前を指定します。|
|[ExpressionBinding の構成 (形式) のコントロールの EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コレクションの要素がコントロールによって表示されることを指定します。|
|[ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> この一般的なコントロールを使用するのに必要な条件を定義します。|
|[ExpressionBinding の構成 (形式) のコントロールの PropertyName 要素](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 値を持つが、一般的なコントロールによって表示される、.NET プロパティを指定します。|
|[ExpressionBinding の構成 (形式) のコントロールの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 値を持つが、一般的なコントロールによって表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールの構成の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|カスタム コントロールのビューで表示するデータと表示方法を定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[コントロールの構成の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
