---
title: CustomControl for ビュー (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 25101c9c156ef91657f51db7044bf9a6653142a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785831"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a>View の CustomControl の CustomEntry の CustomItem 要素 (書式)

カスタムコントロールビューとその表示方法によって表示されるデータを定義します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) CustomControl for view (format) の CustomEntries 要素のビュー (形式) の CustomEntries を指定します。この要素は、CustomEntry for ビュー (形式) の Customentries 要素です。

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomItem` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[View の CustomControl の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|
|[View (Format) のカスタムコントロールの CustomItem の改行要素](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールの表示に空白行を追加します。|
|[CustomControl for ビュー (Format) の CustomItem の Text 要素](./text-element-for-customitem-for-customview-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータに追加のテキストを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View の CustomControl の CustomEntries の CustomEntry 要素 (書式)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|カスタムコントロールビューの定義を提供します。|

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[View (Format) の CustomEntries の CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[View の CustomControl の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[View の CustomControl の CustomItem の NewLine 要素 (書式)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[CustomControl for ビュー (Format) の CustomItem の Text 要素](./text-element-for-customitem-for-customview-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
