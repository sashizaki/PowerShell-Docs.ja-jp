---
title: 構成用コントロールのコントロールの CustomControl 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5aacf824421dfce19f1f495fc0a95e766cdbaf8b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786086"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a>Configuration の Controls の Control の CustomControl 要素 (書式)

コントロールを定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの構成 (format) CustomControl 要素のコントロール要素の構成 (形式) のコントロールの要素

## <a name="syntax"></a>構文

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControl` ます。 この要素には、少なくとも1つの子要素が必要です。 指定できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[Configuration の CustomControl の CustomEntries 要素 (形式)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|必須の要素です。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Configuration の Controls の Control 要素 (書式)](./control-element-for-controls-for-configuration-format.md)|書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。|

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[Configuration の Controls の Control 要素 (書式)](./control-element-for-controls-for-configuration-format.md)

[Configuration の CustomControl の CustomEntries 要素 (形式)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
