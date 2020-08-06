---
title: ビューのコントロール用の CustomControl 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2020725bf6afb086901e14a976abbdc04366869c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786103"
---
# <a name="customcontrol-element-for-control-for-controls-for-view-format"></a>View の Controls の Control の CustomControl 要素 (書式)

ビューによって使用されるコントロールを定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素 (format) を表示するコントロールのコントロール要素 (書式) のコントロール要素

## <a name="syntax"></a>構文

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControl` ます。 子要素を1つだけ指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[View の Controls の CustomControl の CustomEntries 要素 (書式)](./customentries-element-for-customcontrol-for-controls-for-view-format.md)|必須の要素です。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビューのコントロールの Control 要素 (Format)](./control-element-for-controls-for-view-format.md)|ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。|

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[View の CustomControl の CustomEntries 要素 (書式)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[ビューのコントロールの Control 要素 (Format)](./control-element-for-controls-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
