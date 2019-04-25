---
title: コントロールの表示 (形式) の control 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066772"
---
# <a name="control-element-for-controls-for-view--format"></a>View の Controls の Control 要素 (書式)

ビューとコントロールを参照するために使用される名前で使用できるコントロールを定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) では、コントロールの要素 (形式) のコントロール要素を制御表示されます (形式)

## <a name="syntax"></a>構文

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Control`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の name 要素](./name-element-for-control-for-controls-for-view-format.md)|必須の要素。<br /><br /> コントロールの名前を指定します。|
|[コントロールが表示されます (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-view-format.md)|必須の要素。<br /><br /> このビューで使用されるコントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロール要素 (形式)](./controls-element-for-view-format.md)|特定のビューで使用できるビュー コントロールを定義します。|

## <a name="remarks"></a>コメント

このコントロールは、次の要素で指定できます。

- [コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [GroupBy (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [GroupBy (形式) の CustomControlName 要素](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[GroupBy (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (形式) の ExpressionBinding CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[コントロール要素 (形式)](./controls-element-for-view-format.md)

[コントロールが表示されます (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
