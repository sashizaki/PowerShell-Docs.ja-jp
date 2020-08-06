---
title: View (Format) コントロールの CustomEntries の CustomEntry 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4fc960ab803580f684ce0f224b1db4d7d4af1720
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785899"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a>View の Controls の CustomEntries の CustomEntry 要素 (書式)

コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素を表示するコントロールのコントロールの要素 (書式) の CustomControl 要素 (format) ビューのコントロールの CustomEntries の CustomControl for ビュー (形式) のカスタムエントリ要素

## <a name="syntax"></a>構文

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntry` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|
|[View の Controls の CustomEntry の CustomItem 要素 (書式)](./customitem-element-for-customentry-for-controls-for-view-format.md)|必須の要素です。<br /><br /> コントロールがデータを表示する方法を定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View の CustomControl の CustomEntries 要素 (書式)](./customentries-element-for-customcontrol-for-view-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[View の CustomControl の CustomEntries 要素 (書式)](./customentries-element-for-customcontrol-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
