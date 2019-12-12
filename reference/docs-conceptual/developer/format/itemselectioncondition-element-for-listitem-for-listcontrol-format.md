---
title: ListControl の ListItem の ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365191"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の ItemSelectionCondition 要素 (書式)

このリスト項目を使用するために必要な条件を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListControl (format) ListEntry 要素の listentries の ListControl (Format) ListItems 要素の listentries 要素for ListControl (Format) ListItem 要素 for ListItems for ListControl (format) ItemSelectionCondition Element for ListControl (Format)

## <a name="syntax"></a>構文

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ItemSelectionCondition` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[ListControl の ItemSelectionCondition の PropertyName 要素 (形式)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[ListControl の ItemSelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListControl の ListItems の ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)|リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。|

## <a name="remarks"></a>コメント

この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[ListControl の ListItems の ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)

[ListControl の ItemSelectionCondition の PropertyName 要素 (形式)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[ListControl の ItemSelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
