---
title: ビュー用のコントロールの CustomItem の Frame 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363651"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a>View の Controls の CustomItem の Frame 要素 (書式)

データを左右に移動するなど、データの表示方法を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (Format) のコントロールに対して Customentries のビュー (format) フレーム要素のビュー (書式) の Customentries 要素のコントロールの CustomEntries 要素を表示します。

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
|[ビューのコントロールのフレームの FirstLineHanging 要素 (形式)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> 最初の行を左にシフトする文字数を指定します。|
|[ビューのコントロールのフレームの FirstLineIndent 要素 (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> 最初の行を右にシフトする文字数を指定します。|
|[ビューのコントロールのフレームの左インデント要素 (書式)](./leftindent-element-for-frame-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> データを左余白から移動する文字数を指定します。|
|[ビューのコントロールのフレームの右インデント要素 (書式)](./rightindent-element-for-frame-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> データを右余白から移動する文字数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-controls-for-view-format.md)|コントロールによって表示されるデータとその表示方法を定義します。|

## <a name="remarks"></a>コメント

[Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素を同じ `Frame` 要素で指定することはできません。

## <a name="see-also"></a>参照

[ビューのコントロールのフレームの FirstLineHanging 要素 (形式)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[ビューのコントロールのフレームの FirstLineIndent 要素 (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[ビューのコントロールのフレームの左インデント要素 (書式)](./leftindent-element-for-frame-for-controls-for-view-format.md)

[ビューのコントロールのフレームの右インデント要素 (書式)](./rightindent-element-for-frame-for-controls-for-view-format.md)

[ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
