---
title: GroupBy (Format) の CustomItem の Frame 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362951"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>GroupBy の CustomItem の Frame 要素 (書式)

データを左右に移動するなど、データの表示方法を定義します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (形式) の CustomItem の groupby (format) Frame 要素の CustomControl for groupby (format) の CustomItem 要素

## <a name="syntax"></a>構文

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`Frame` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|`CustomItem Element`|必須の要素|
|[GroupBy (Format) の Frame の FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-groupby-format.md)|省略可能な要素。<br /><br /> データの最初の行を左にシフトする文字数を指定します。|
|[GroupBy (Format) の Frame の FirstLineIndent 要素](./firstlineindent-element-for-frame-for-groupby-format.md)|省略可能な要素。<br /><br /> データの最初の行を右にシフトする文字数を指定します。|
|[GroupBy (Format) の Frame の左インデント要素](./leftindent-element-for-frame-for-groupby-format.md)|省略可能な要素。<br /><br /> データを左余白から移動する文字数を指定します。|
|[GroupBy (Format) の Frame の右インデント要素](./rightindent-element-for-frame-for-groupby-format.md)右インデント要素|省略可能な要素。<br /><br /> データを右余白から移動する文字数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy の CustomEntry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-groupby-format.md)|コントロールによって表示されるデータとその表示方法を定義します。|

## <a name="remarks"></a>コメント

[Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-groupby-format.md)要素を同じ `Frame` 要素で指定することはできません。

## <a name="see-also"></a>参照

[GroupBy (Format) の Frame の FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-groupby-format.md)

[GroupBy (Format) の Frame の FirstLineIndent 要素](./firstlineindent-element-for-frame-for-groupby-format.md)

[GroupBy (Format) の Frame の左インデント要素](./leftindent-element-for-frame-for-groupby-format.md)

[GroupBy (Format) の Frame の右インデント要素](./rightindent-element-for-frame-for-groupby-format.md)

[GroupBy の CustomEntry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
