---
title: 構成用のコントロールのフレームの FirstLineIndent 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9ac1d8dc74af12b87f0b490d7c1f75d028e3521f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773591"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a>Configuration の Controls の Frame の FirstLineIndent 要素 (書式)

データの最初の行を右にシフトする文字数を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成 (形式) の CustomControl の構成 (書式) の CustomEntries 要素のコントロール要素 CustomControl for Controls の構成 (書式) Customentries 要素のコントロール用の構成フレーム要素の構成用コントロールの構成 (形式) の Customlineindent 要素を構成するためのコントロールのためのフレーム (形式)

## <a name="syntax"></a>構文

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Configuration の Controls の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|データを左右に移動するなど、データの表示方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>解説

この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[Configuration の Controls の Frame の FirstLineHanging 要素 (書式)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Configuration の Controls の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
