---
title: コントロールが表示されます (形式) のフレームの FirstLineIndent 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec63f4f9-8858-4529-8646-ffbbc278f83e
caps.latest.revision: 7
ms.openlocfilehash: 694c5baaa5e90a772257276ba139d90acf7ec0e3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854318"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a>View の Controls の Frame の FirstLineIndent 要素 (書式)

データの最初の行が右側にシフトした文字数を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem のフレームのビュー (形式) FirstLineIndent 要素のコントロールのビュー (形式) フレーム要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールビュー (形式) のコントロールの

## <a name="syntax"></a>構文

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineIndent`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-view-format.md)|データを左または右にシフトなど、データを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>コメント

この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)要素。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
