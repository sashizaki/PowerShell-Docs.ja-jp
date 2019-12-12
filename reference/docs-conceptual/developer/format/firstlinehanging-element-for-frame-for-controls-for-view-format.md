---
title: ビューのコントロールのフレームの FirstLineHanging 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53694f08-57f7-4185-b443-1636a0918afc
caps.latest.revision: 8
ms.openlocfilehash: 387340cd9b0aae2ad0419b187d96ab4fee183d5a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363791"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a>View の Controls の Frame の FirstLineHanging 要素 (書式)

データの最初の行を左にシフトする文字数を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (format) の customentries 要素に対して、コントロールのビュー (format) Frame 要素のコントロールのビュー (形式) の customentries 要素を表示します。ビューのコントロールのフレーム (書式)

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
|[ビューのコントロールの CustomItem の Frame 要素 (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)|データを左右に移動するなど、データの表示方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>コメント

この要素が指定されている場合、 [Firstlineindent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[ビューのコントロールのフレームの FirstLineIndent 要素 (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[ビューのコントロールの CustomItem の Frame 要素 (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
