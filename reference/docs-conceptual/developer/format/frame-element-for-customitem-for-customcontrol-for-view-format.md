---
title: CustomControl for ビュー (Format) の CustomItem の Frame 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: 925ef86e61801f5a66f89dd25e0756f00dd35155
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363641"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>View の CustomControl の CustomItem の Frame 要素 (書式)

データを左右に移動するなど、データの表示方法を定義します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for ビュー (Format) の CustomItem for CustomControlView (Format) Frame 要素のための CustomEntry

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

次のセクションでは、`Frame` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|`CustomItem Element`|必須の要素|
|[FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> データの最初の行を左にシフトする文字数を指定します。|
|[FirstLineIndent 要素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> データの最初の行を右にシフトする文字数を指定します。|
|[左インデント要素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> データを左余白から移動する文字数を指定します。|
|[右インデント要素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> データを右余白から移動する文字数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomEntry for ビューの CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|コントロールによって表示されるデータとその表示方法を定義します。|

## <a name="remarks"></a>コメント

同じ `Frame` 要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[FirstLineIndent 要素](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[左インデント要素](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[右インデント要素](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[CustomEntry for ビューの CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
