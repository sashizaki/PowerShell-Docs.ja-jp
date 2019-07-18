---
title: GroupBy (形式) の ExpressionBinding CustomControlName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e11da8f-1e75-4d3d-b4c8-b500dec3028e
caps.latest.revision: 6
ms.openlocfilehash: 32f8a71e9818c8c1a052f3b96f442f169c1bda4a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066570"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a>GroupBy の ExpressionBinding の CustomControlName 要素 (書式)

一般的なコントロールまたはビューのコントロールの名前を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) の GroupBy (形式) CustomControlName 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール

## <a name="syntax"></a>構文

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-groupby-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="text-value"></a>テキスト値

コントロールの名前を指定します。

## <a name="remarks"></a>コメント

書式設定ファイルでは、すべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。 次の要素は、これらのコントロールの名前を指定します。

- [構成 (形式) のコントロールのコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)

- [コントロールが表示されます (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[構成 (形式) のコントロールのコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)

[コントロールが表示されます (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-view-format.md)

[GroupBy (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
