---
title: コントロールの構成 (形式) のフレームの FirstLineIndent 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f489720-11f6-4019-940e-07f423d4278d
caps.latest.revision: 6
ms.openlocfilehash: c5b2d971fe1590116f96b024ae8769334768acf2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856348"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a>Configuration の Controls の Frame の FirstLineIndent 要素 (書式)

データの最初の行が右側にシフトした文字数を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素CustomEntry CustomItem のフレームの構成 (形式) FirstLineIndent 要素のコントロールの構成のフレーム要素のコントロール用の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素コントロールの構成 (形式)

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
|[構成 (形式) のコントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-configuration-format.md)|データを左または右にシフトなど、データを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>コメント

この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)要素。

## <a name="see-also"></a>参照

[コントロールの構成 (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
