---
title: ListControl の ItemSelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8bdbb05326f7ff5ccffa46215631a5c954080dc1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780867"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>ListControl の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、ビューが使用されます。 この要素は、リストビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) ListControl Element (format) ListEntries Element (format) ListEntry 要素 for ListEntry (format) ListControl (format) ListItems 要素の ListControl for ListItems (format) 項目の (format) 項目の listitem 要素の ListItem 要素の Listentries の (形式)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl の ListItem の ItemSelectionCondition 要素 (書式)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>テキスト値

値が表示されるプロパティの名前を指定します。

## <a name="remarks"></a>解説

この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[ListIControl の ItemSelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[ListControl の ListItem の ItemSelectionCondition 要素 (書式)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
