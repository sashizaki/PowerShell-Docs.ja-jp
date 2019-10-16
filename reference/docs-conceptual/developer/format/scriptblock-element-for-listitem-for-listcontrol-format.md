---
title: ListControl の ListItem の ScriptBlock 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364811"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の ScriptBlock 要素 (書式)

行に値が表示されるスクリプトを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListControl (format) ListEntry 要素の listentries の ListControl (Format) ListItems 要素の listentries 要素for ListControl (Format) ListItem 要素 for ListItems for ListControl (Format) ScriptBlock for ListControl (Format)

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)|リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

行に値が表示されるスクリプトを指定します。

## <a name="remarks"></a>コメント

この要素が指定されている場合、 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素を指定することはできません。

リストビューでのスクリプトの指定の詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、値が表示されるプロパティを指定する方法を示しています。

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>参照

[ListControl の ListItem の PropertyName 要素 (形式)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[リストビューの作成](./creating-a-list-view.md)

[ListControl の ListItems の ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
