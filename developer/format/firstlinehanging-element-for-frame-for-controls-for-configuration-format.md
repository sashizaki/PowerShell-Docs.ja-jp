---
title: コントロールの構成 (形式) のフレームの FirstLineHanging 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679c8bcb-b49d-4bb4-91f5-ea1af6c217e3
caps.latest.revision: 8
ms.openlocfilehash: 4553f95e48a2b1440c00b4951bea56376b00628a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065888"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a>Configuration の Controls の Frame の FirstLineHanging 要素 (書式)

データの最初の行が左にシフト文字の数を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素CustomEntry CustomItem のフレームの構成 (形式) FirstLineHanging 要素のコントロールの構成のフレーム要素のコントロール用の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素コントロールの構成 (形式)

## <a name="syntax"></a>構文

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineHanging`要素。

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

この要素が指定されているかどうかは指定できません、`FirstLineIndent`要素。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
