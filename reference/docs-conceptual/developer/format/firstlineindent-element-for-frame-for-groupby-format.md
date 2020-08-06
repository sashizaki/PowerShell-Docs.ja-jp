---
title: GroupBy (Format) の Frame の FirstLineIndent 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: def5b4e9ca98a15edbb36675ca506e886de567dc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781666"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a>GroupBy の Frame の FirstLineIndent 要素 (書式)

データの最初の行を右にシフトする文字数を指定します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素を groupby (形式) CustomEntry の CustomControl の CustomEntries 要素 groupby (書式) のための groupby (format) の Customentries 要素の groupby (format) フレーム要素の CustomControl のための要素に対する groupby (Format) の Customentries 要素の設定 groupby (形式) の Frame の要素

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
|[GroupBy の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-groupby-format.md)|データを左右に移動するなど、データの表示方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>解説

この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[GroupBy の Frame の FirstLineHanging 要素 (書式)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[GroupBy の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-groupby-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
