---
title: ScriptBlock ListControl (形式) を ListItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855558"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の ScriptBlock 要素 (書式)

行の値が表示されるスクリプトを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries ListEntry の ListControl (形式) のリスト項目要素のListControl (形式) を ListItem の ListControl (形式) スクリプト ブロックの要素の ListItems の ListItem 要素を ListControl (形式)

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)|プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

行の値が表示されるスクリプトを指定します。

## <a name="remarks"></a>コメント

この要素が指定されている場合は指定できません、 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素。

リスト ビューでスクリプトを指定する方法については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。

## <a name="example"></a>例

次の例では、値が表示されるプロパティを指定する方法を示します。

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>参照

[PropertyName ListControl (形式) を ListItem 要素](./propertyname-element-for-listitem-for-listcontrol-format.md)

[リスト ビューの作成](./creating-a-list-view.md)

[ListControl (形式) のリスト項目の ListItem 要素](./listitem-element-for-listitems-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
