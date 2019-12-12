---
title: CustomControl for View (Format) のフレームの FirstLineHanging 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6ac3d86-0529-4b93-9bc7-ee94fcef9618
caps.latest.revision: 8
ms.openlocfilehash: ea43e025f5f653ff000e1d7591b535e73da5c9e5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363161"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a>View の CustomControl の Frame の FirstLineHanging 要素 (書式)

データの最初の行を左にシフトする文字数を指定します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for View (Format) のフレームの CustomControl for ビュー (形式) の FirstLineHanging 要素に関する CustomEntry for CustomControlView (Format) Frame 要素

## <a name="syntax"></a>構文

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`FirstLineHanging` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl for ビュー (Format) の CustomItem の Frame 要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|データを左右に移動するなど、データの表示方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>コメント

この要素が指定されている場合、 [Firstlineindent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[CustomControl for View (Format) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[CustomControl for ビュー (Format) の CustomItem の Frame 要素](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
