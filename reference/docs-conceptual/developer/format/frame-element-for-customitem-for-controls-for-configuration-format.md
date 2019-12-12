---
title: 構成用のコントロールの CustomItem の Frame 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363661"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Configuration の Controls の CustomItem の Frame 要素 (書式)

データを左右に移動するなど、データの表示方法を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl のための CustomEntry 要素を構成するためのコントロールのための CustomEntry 要素を構成するためのコントロールの CustomItem 要素 (形式)

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
|[構成対象のコントロールのフレームの FirstLineHanging 要素 (形式)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データの最初の行を左にシフトする文字数を指定します。|
|[構成対象のコントロールのフレームの FirstLineIndent 要素 (形式)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データの最初の行を右にシフトする文字数を指定します。|
|[構成対象のコントロールのフレームの左インデント要素 (形式)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データを左余白から移動する文字数を指定します。|
|[構成対象のコントロールのフレームの右インデント要素 (形式)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データを右余白から移動する文字数を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[構成のための CustomEntry コントロールの CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|コントロールによって表示されるデータとその表示方法を定義します。|

## <a name="remarks"></a>コメント

同じ `Frame` 要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[構成対象のコントロールのフレームの FirstLineHanging 要素 (形式)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[構成対象のコントロールのフレームの FirstLineIndent 要素 (形式)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[構成対象のコントロールのフレームの左インデント要素 (形式)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[構成対象のコントロールのフレームの右インデント要素 (形式)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[構成のための CustomEntry コントロールの CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
