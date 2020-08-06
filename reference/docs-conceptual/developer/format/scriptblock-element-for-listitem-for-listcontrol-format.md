---
title: ListControl の ListItem の ScriptBlock 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785457"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の ScriptBlock 要素 (書式)

行に値が表示されるスクリプトを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) の listentries ListControl (format) ListItems 要素の ListEntries for ListEntry (format) ListEntry 要素の ListControl for ListItems (format) の listitem 要素の ListControl for ListControl (形式) の ListItem 要素

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)|リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

行に値が表示されるスクリプトを指定します。

## <a name="remarks"></a>解説

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

[ListControl の ListItem の PropertyName 要素 (書式)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[リスト ビューを作成する](./creating-a-list-view.md)

[ListControl の ListItems の ListItem 要素 (書式)](./listitem-element-for-listitems-for-listcontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
