---
title: ListItem 要素の ListItems ListControl (形式) の |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f96f4f5-8bd5-43ed-95e7-a7358115999a
caps.latest.revision: 11
ms.openlocfilehash: 1e0a1b2d20853650328b8cfd1513a08f7e167cd6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855158"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a>ListControl の ListItems の ListItem 要素 (書式)

プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListControl (形式) のリスト項目要素を ListControl (形式)ListItem ListControl 要素 (形式)

## <a name="syntax"></a>構文

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ListItem`要素。 1 つだけのプロパティまたはスクリプトを指定することができます。

### <a name="attributes"></a>属性

None

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) を ListItem の FormatString 要素](./formatstring-element-for-listitem-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> プロパティまたはスクリプトの値を表示する方法を定義する書式指定文字列を指定します。|
|[ItemSelectionCondition ListControl (形式) を ListItem 要素](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 使用するには、このリスト項目の存在する必要がある条件を定義します。|
|[Label ListControl (形式) を ListItem 要素](./label-element-for-listitem-for-listcontrol-format.md)|省略可能な要素<br /><br /> 行のプロパティまたはスクリプトの値の左側に表示されるラベルを指定します。|
|[PropertyName ListControl (形式) を ListItem 要素](./propertyname-element-for-listitem-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 行の値が表示される、.NET プロパティを指定します。|
|[ScriptBlock ListControl (形式) を ListItem 要素](./scriptblock-element-for-listitem-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 行の値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[リスト コントロール (形式) のリスト項目要素](./listitems-element-for-listentry-for-listcontrol-format.md)|プロパティと値を持つが、一覧に表示されるスクリプトを定義します。|

## <a name="remarks"></a>コメント

リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

## <a name="example"></a>例

この例では、リスト ビューの 3 つの行を定義する XML 要素を示します。 最初の 2 つの行は、.NET プロパティの値を表示し、最後の行がスクリプトによって生成される値を表示します。

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a>参照

[リスト項目要素 (形式)](./listitems-element-for-listentry-for-listcontrol-format.md)

[ListItem (形式) の FormatString 要素](./formatstring-element-for-listitem-for-listcontrol-format.md)

[ListItem (形式) のラベル要素](./label-element-for-listitem-for-listcontrol-format.md)

[ListItem (形式) の PropertyName 要素](./propertyname-element-for-listitem-for-listcontrol-format.md)

[ListItem (形式) の ScriptBlock 要素](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[リスト ビューの作成](./creating-a-list-view.md)

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
