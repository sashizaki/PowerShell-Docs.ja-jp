---
title: GroupBy (形式) のフレームの FirstLineIndent 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33be3b9e-53c8-433f-8c11-c65b0d46744c
caps.latest.revision: 6
ms.openlocfilehash: 9ba6fc1b9924a4b0d5b56ee15290a2293217403c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858558"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a>GroupBy の Frame の FirstLineIndent 要素 (書式)

データの最初の行が右側にシフトした文字数を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) のフレームの GroupBy (形式) FirstLineIndent 要素 CustomItem の GroupBy (形式) フレーム要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール

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
|[GroupBy (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-groupby-format.md)|データを左または右にシフトなど、データを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>コメント

この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)要素。

## <a name="see-also"></a>参照

[GroupBy (形式) のフレームの FirstLineHanging 要素](./firstlinehanging-element-for-frame-for-groupby-format.md)

[GroupBy (形式) の CustomItem フレーム要素](./frame-element-for-customitem-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
