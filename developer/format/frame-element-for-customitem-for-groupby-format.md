---
title: CustomItem の GroupBy (形式) の要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854848"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>GroupBy の CustomItem の Frame 要素 (書式)

データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の CustomItem の GroupBy (形式) フレーム要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール

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

次のセクションでは、属性、子要素、およびの親要素について説明します、`Frame`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|`CustomItem Element`|必要な要素|
|[GroupBy (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-groupby-format.md)|省略可能な要素です。<br /><br /> データの最初の行が左にシフト文字の数を指定します。|
|[GroupBy (形式) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-groupby-format.md)|省略可能な要素です。<br /><br /> データの最初の行が右側にシフトした文字数を指定します。|
|[GroupBy (形式) のフレームの LeftIndent 要素](./leftindent-element-for-frame-for-groupby-format.md)|省略可能な要素です。<br /><br /> 左余白からデータを移動する文字の数を指定します。|
|[GroupBy (形式) のフレームの RightIndent 要素](./rightindent-element-for-frame-for-groupby-format.md)RightIndent 要素|省略可能な要素です。<br /><br /> 右の余白からデータを移動する文字の数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-groupby-format.md)|どのようなデータが、コントロールによって表示され、表示方法を定義します。|

## <a name="remarks"></a>コメント

指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md)要素で同じ`Frame`要素。

## <a name="see-also"></a>参照

[GroupBy (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-groupby-format.md)

[GroupBy (形式) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-groupby-format.md)

[GroupBy (形式) のフレームの LeftIndent 要素](./leftindent-element-for-frame-for-groupby-format.md)

[GroupBy (形式) のフレームの RightIndent 要素](./rightindent-element-for-frame-for-groupby-format.md)

[GroupBy (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
