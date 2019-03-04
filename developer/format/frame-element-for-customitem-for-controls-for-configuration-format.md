---
title: CustomItem の構成 (形式) のコントロールの要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862978"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Configuration の Controls の CustomItem の Frame 要素 (書式)

データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成フレーム要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素

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
|[コントロールの構成 (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データの最初の行が左にシフト文字の数を指定します。|
|[コントロールの構成 (形式) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データの最初の行が右側にシフトした文字数を指定します。|
|[コントロールの構成 (形式) のフレームの LeftIndent 要素](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 左余白からデータを移動する文字の数を指定します。|
|[コントロールの構成 (形式) のフレームの RightIndent 要素](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 右の余白からデータを移動する文字の数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールの構成の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|どのようなデータが、コントロールによって表示され、表示方法を定義します。|

## <a name="remarks"></a>コメント

指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)要素で同じ`Frame`要素。

## <a name="see-also"></a>参照

[コントロールの構成 (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[コントロールの構成 (形式) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[コントロールの構成 (形式) のフレームの LeftIndent 要素](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[コントロールの構成 (形式) のフレームの RightIndent 要素](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[コントロールの構成の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
