---
title: ListControl の ItemSelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e707ae-3c84-4ceb-ba31-56b3ffde6d6c
caps.latest.revision: 7
ms.openlocfilehash: b15e26e18126f69eee7c3a857f9a461d4bdf5848
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362391"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>ListControl の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、ビューが使用されます。 この要素は、リストビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry の ListControl (Format) ListItems 要素の (format) ListItem の要素ListControl (Format) の ItemSelectionCondition の ListControls PropertyName 要素の ListItems for ListControl (Format) ItemSelectionCondition 要素の要素

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListControl の ListItem の ItemSelectionCondition 要素 (形式)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>テキスト値

値が表示されるプロパティの名前を指定します。

## <a name="remarks"></a>コメント

この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[ListIControl の ItemSelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[ListControl の ListItem の ItemSelectionCondition 要素 (形式)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
