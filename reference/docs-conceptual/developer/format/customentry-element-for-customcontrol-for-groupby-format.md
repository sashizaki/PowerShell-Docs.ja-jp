---
title: GroupBy (Format) の CustomControl の CustomEntry 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2987cb45-f646-45d4-b81b-7871e77af36f
caps.latest.revision: 5
ms.openlocfilehash: dcf4f8b2bbd422067ffdf9b3b4972e279e91edf9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364061"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a>GroupBy の CustomControl の CustomEntry 要素 (書式)

コントロールの定義を提供します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素GroupBy (Format) の CustomControl

## <a name="syntax"></a>構文

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomEntry` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-customentry-for-groupby-format.md)|省略可能な要素。<br /><br /> このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|
|[GroupBy の CustomEntry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-groupby-format.md)|必須の要素です。<br /><br /> コントロールがデータを表示する方法を定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomControl の CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[GroupBy の CustomEntry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-groupby-format.md)

[GroupBy (Format) の CustomControl の CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
