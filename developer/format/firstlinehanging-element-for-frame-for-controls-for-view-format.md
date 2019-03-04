---
title: コントロールが表示されます (形式) のフレームの FirstLineHanging 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53694f08-57f7-4185-b443-1636a0918afc
caps.latest.revision: 8
ms.openlocfilehash: 387340cd9b0aae2ad0419b187d96ab4fee183d5a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858718"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a>View の Controls の Frame の FirstLineHanging 要素 (書式)

データの最初の行が左にシフト文字の数を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem のビュー (形式) FirstLineHanging 要素のコントロールのビュー (形式) フレーム要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールビュー (形式) のコントロールのフレーム

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
|[コントロールが表示されます (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-view-format.md)|データを左または右にシフトなど、データを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>コメント

この要素が指定されているかどうかは指定できません、 [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) のフレームの FirstLineIndent 要素](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
