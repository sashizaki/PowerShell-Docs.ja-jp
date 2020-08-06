---
title: View (Format) 用のコントロールの CustomControl の CustomEntries 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a52bd2368044c34a0b73da331785d55597e30260
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783706"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>View の Controls の CustomControl の CustomEntries 要素 (書式)

コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (形式) コントロールのコントロールの要素 (書式) のコントロール要素 (format) のコントロールの CustomControl 要素 (format) のコントロールのコントロール要素 (形式) のコントロールの CustomControl

## <a name="syntax"></a>構文

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntries` ます。 指定できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[View の Controls の CustomEntries の CustomEntry 要素 (書式)](./customentry-element-for-customentries-for-controls-for-view-format.md)|必須の要素です。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View の Controls の Control の CustomControl 要素 (書式)](./customcontrol-element-for-control-for-controls-for-view-format.md)|ビューによって使用されるコントロールを定義します。|

## <a name="remarks"></a>解説

ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で指定され `CustomEntry` ます。 ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。 そのような場合は、 `CustomEntry` オブジェクトまたはオブジェクトのセットごとに要素を定義できます。

## <a name="see-also"></a>参照

[View の Controls の CustomEntries の CustomEntry 要素 (書式)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[View の Controls の Control の CustomControl 要素 (書式)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
