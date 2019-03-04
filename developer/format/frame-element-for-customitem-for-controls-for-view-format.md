---
title: CustomItem の表示 (形式) のコントロールの要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859818"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a>View の Controls の CustomItem の Frame 要素 (書式)

データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) フレーム要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロール

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
|[ビュー (形式) のコントロールのフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 最初の行が左にシフト文字の数を指定します。|
|[ビュー (形式) のコントロールのフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 最初の行が右側にシフト文字の数を指定します。|
|[ビュー (形式) のコントロールのフレームの LeftIndent 要素](./leftindent-element-for-frame-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 左余白からデータを移動する文字の数を指定します。|
|[ビュー (形式) のコントロールのフレームの RightIndent 要素](./rightindent-element-for-frame-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 右の余白からデータを移動する文字の数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-view-format.md)|どのようなデータが、コントロールによって表示され、表示方法を定義します。|

## <a name="remarks"></a>コメント

指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素で同じ`Frame`要素。

## <a name="see-also"></a>参照

[ビュー (形式) のコントロールのフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[ビュー (形式) のコントロールのフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[ビュー (形式) のコントロールのフレームの LeftIndent 要素](./leftindent-element-for-frame-for-controls-for-view-format.md)

[ビュー (形式) のコントロールのフレームの RightIndent 要素](./rightindent-element-for-frame-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
