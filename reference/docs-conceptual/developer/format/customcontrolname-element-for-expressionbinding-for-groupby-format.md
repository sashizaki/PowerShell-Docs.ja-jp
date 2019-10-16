---
title: GroupBy (Format) の式のバインドの CustomControlName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e11da8f-1e75-4d3d-b4c8-b500dec3028e
caps.latest.revision: 6
ms.openlocfilehash: 32f8a71e9818c8c1a052f3b96f442f169c1bda4a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368911"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a>GroupBy の ExpressionBinding の CustomControlName 要素 (書式)

コモンコントロールまたはビューコントロールの名前を指定します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (format) 式のバインド要素 groupby (形式) の式のバインドのための、GroupBy (format) CustomControlName 要素

## <a name="syntax"></a>構文

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`CustomControlName` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-groupby-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="text-value"></a>テキスト値

コントロールの名前を指定します。

## <a name="remarks"></a>コメント

書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。 次の要素は、これらのコントロールの名前を指定します。

- [構成用コントロールのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [ビューのコントロールに対する Control の Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[構成用コントロールのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[ビューのコントロールに対する Control の Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)

[GroupBy (Format) の CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
