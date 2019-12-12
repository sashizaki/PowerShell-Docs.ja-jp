---
title: CustomControl for ビュー (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363951"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a>View の CustomControl の CustomEntry の CustomItem 要素 (書式)

カスタムコントロールビューとその表示方法によって表示されるデータを定義します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomEntry ビュー (形式)

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomItem` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[CustomControl for ビュー (Format) の CustomItem の Frame 要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|
|[View (Format) のカスタムコントロールの CustomItem の改行要素](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールの表示に空白行を追加します。|
|[CustomControl for ビュー (Format) の CustomItem の Text 要素](./text-element-for-customitem-for-customview-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータに追加のテキストを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl for ビュー (Format) の CustomEntries の CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|カスタムコントロールビューの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[View (Format) の CustomEntries の CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[CustomControl for ビュー (Format) の CustomItem の Frame 要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[CustomControl for ビュー (Format) の CustomItem の改行要素](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[CustomControl for ビュー (Format) の CustomItem の Text 要素](./text-element-for-customitem-for-customview-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
