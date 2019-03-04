---
title: CustomItem の表示 (形式) のカスタム コントロールの要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: a7ee550527ec1cb00b4ed83478992c7ab54dbdb6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861708"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>View の CustomControl の CustomItem の Frame 要素 (書式)

データを左または右にシフトなど、データを表示する方法を定義します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem ビュー (形式) のカスタム コントロール用のフレーム要素を CutomControlView (形式)

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
|[FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> データの最初の行が左にシフト文字の数を指定します。|
|[FirstLineIndent 要素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> データの最初の行が右側にシフトした文字数を指定します。|
|[LeftIndent 要素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 左余白からデータを移動する文字の数を指定します。|
|[RightIndent 要素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> 右の余白からデータを移動する文字の数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[表示 (形式) CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|どのようなデータが、コントロールによって表示され、表示方法を定義します。|

## <a name="remarks"></a>コメント

指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素で同じ`Frame`要素。

## <a name="see-also"></a>参照

[FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[FirstLineIndent 要素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[LeftIndent 要素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[RightIndent 要素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[表示 (形式) CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
