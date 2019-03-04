---
title: ビュー (形式) のカスタム コントロールのフレームの FirstLineHanging 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6ac3d86-0529-4b93-9bc7-ee94fcef9618
caps.latest.revision: 8
ms.openlocfilehash: ae4ad8ae3e6cb5d1174dc001b30aa84dd182a606
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860238"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a>View の CustomControl の Frame の FirstLineHanging 要素 (書式)

データの最初の行が左にシフト文字の数を指定します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem ビュー (形式) のカスタム コントロールのフレームのビュー (形式) FirstLineHanging 要素のカスタム コントロール用のフレーム要素を CutomControlView (形式)

## <a name="syntax"></a>構文

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineHanging`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のカスタム コントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|データを左または右にシフトなど、データを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>コメント

この要素が指定されているかどうかは指定できません、 [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素。

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールのフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
