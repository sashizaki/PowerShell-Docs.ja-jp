---
title: PropertyName ListControl (形式) を ListItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01ae8cbe-acdc-4043-bd6e-1118a5691a55
caps.latest.revision: 12
ms.openlocfilehash: 405184f7bdbf1955f1df7766bf2723c244dcc27f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064919"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の PropertyName 要素 (書式)

値が一覧に表示、.NET プロパティを指定します。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) ListItems 要素 (形式) ListItem 要素 (形式) PropertyName の構成要素ListItem (形式)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)|プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

値が表示されるプロパティの名前を指定します。

## <a name="remarks"></a>コメント

この要素が指定されている場合は指定できません、 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素。

プロパティの値を表示するだけでなく、値または値の表示を変更するために使用する書式指定文字列のラベルを指定することもできます。 リスト ビューでデータを指定する方法については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

## <a name="example"></a>例

次の例では、ラベルと値が表示されるプロパティを指定する方法を示します。

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a>参照

[ScriptBlock ListControl (形式) を ListItem 要素](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[リスト ビューの作成](./creating-a-list-view.md)

[ListControl(Format) の ListItem 要素](./listitem-element-for-listitems-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
