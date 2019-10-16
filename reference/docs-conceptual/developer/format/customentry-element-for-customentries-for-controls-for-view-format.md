---
title: View (Format) コントロールの CustomEntries の CustomEntry 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364051"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a>View の Controls の CustomEntries の CustomEntry 要素 (書式)

コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for View (Format) CustomEntry 要素 (ビューのコントロールの CustomEntries の場合)

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
|[ビューのコントロールに対する CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|
|[ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-controls-for-view-format.md)|必須の要素です。<br /><br /> コントロールがデータを表示する方法を定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl for View (Format) の CustomEntries 要素](./customentries-element-for-customcontrol-for-view-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[CustomControl for View (Format) の CustomEntries 要素](./customentries-element-for-customcontrol-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
