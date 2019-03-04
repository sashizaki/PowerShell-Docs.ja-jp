---
title: ItemSelectionCondition ListControl (形式) を ListItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861868"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の ItemSelectionCondition 要素 (書式)

使用するには、このリスト項目の存在する必要がある条件を定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries ListEntry の ListControl (形式) のリスト項目要素のListControl (形式) を ListItem の ListControl (形式) ItemSelectionCondition 要素の ListItems の ListItem 要素を ListControl (形式)

## <a name="syntax"></a>構文

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[PropertyName ItemSelectionCondition ListControl (形式) の要素](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[ItemSelectionCondition ListControl (形式) 用のスクリプト ブロックの要素](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) のリスト項目の ListItem 要素](./listitem-element-for-listitems-for-listcontrol-format.md)|プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。|

## <a name="remarks"></a>コメント

1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[ListControl (形式) のリスト項目の ListItem 要素](./listitem-element-for-listitems-for-listcontrol-format.md)

[PropertyName ItemSelectionCondition ListControl (形式) の要素](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[ItemSelectionCondition ListControl (形式) 用のスクリプト ブロックの要素](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
