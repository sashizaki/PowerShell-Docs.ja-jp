---
title: PropertyName ItemSelectionCondition ListControl (形式) の要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e707ae-3c84-4ceb-ba31-56b3ffde6d6c
caps.latest.revision: 7
ms.openlocfilehash: b15e26e18126f69eee7c3a857f9a461d4bdf5848
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855538"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>ListControl の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする、.NET プロパティを指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、ビューを使用します。 この要素は、リスト ビューを定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 ListControl (形式) ListItem の ListEntry の ListControl (形式) のリスト項目要素ListItem ItemSelectionCondition ListControl (形式) 用の ListControls PropertyName 要素に対して ListControl (形式) ItemSelectionCondition 要素の ListItems 要素

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ItemSelectionCondition ListControl (形式) を ListItem 要素](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>テキスト値

値が表示されるプロパティの名前を指定します。

## <a name="remarks"></a>コメント

指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)要素の選択条件を定義するときにします。

## <a name="see-also"></a>参照

[ItemSelectionCondition ListIControl (形式) 用のスクリプト ブロックの要素](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[ItemSelectionCondition ListControl (形式) を ListItem 要素](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
