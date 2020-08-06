---
title: ListControl の ListItem の ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f5c388928668e03b96923130fb5849f637548f12
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783621"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の ItemSelectionCondition 要素 (書式)

このリスト項目を使用するために必要な条件を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries for ListItems (format) ListEntry 要素の ListControl (format) ListEntry 要素の ListEntries for ListControl (format) の ListItem 要素の ListItems for ListControl (format) ItemSelectionCondition 要素 for ListControl (Format)

## <a name="syntax"></a>構文

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListControl の ItemSelectionCondition の PropertyName 要素 (書式)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl の ListItems の ListItem 要素 (書式)](./listitem-element-for-listitems-for-listcontrol-format.md)|リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。|

## <a name="remarks"></a>解説

この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[ListControl の ListItems の ListItem 要素 (書式)](./listitem-element-for-listitems-for-listcontrol-format.md)

[ListControl の ItemSelectionCondition の PropertyName 要素 (書式)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
