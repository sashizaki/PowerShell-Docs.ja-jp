---
title: ExpressionBinding 要素のビュー (形式) のカスタム コントロールの CustomItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065922"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素の表示 (カスタム コントロールの CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry CustomItem ビュー (形式) のカスタム コントロール用のビュー (形式) ExpressionBinding 要素のカスタム コントロール用の形式) CustomItem 要素

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

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ExpressionBinding`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|`CustomControl Element`|省略可能な要素です。<br /><br /> このコントロールで使用されるコントロールを定義します。|
|[ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 一般的なコントロールまたはビューのコントロールの名前を指定します。|
|[ビュー (形式) のカスタム コントロールの ExpressionBinding EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コレクションの要素が表示されることを指定します。|
|[ビュー (形式) のカスタム コントロールの ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|省略可能な要素です。<br /><br /> このコントロールを使用するのに必要な条件を定義します。|
|[ビュー (形式) のカスタム コントロールの ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 値を持つが、コントロールによって表示される、.NET プロパティを指定します。|
|[表示 (形式) CustomCustomControl ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 値を持つが、コントロールによって表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|カスタム コントロールのビューで表示するデータと表示方法を定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの ExpressionBinding EnumerateCollection 要素](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの ExpressionBinding ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[ビュー (形式) のカスタム コントロールの ExpressionBinding の PropertyName 要素](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの ExpressionBinding の ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
