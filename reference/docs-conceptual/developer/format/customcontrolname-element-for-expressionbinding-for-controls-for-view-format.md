---
title: ビューのコントロールの式のバインドの CustomControlName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b6ee11e-9086-41d2-afd3-42fb9f24da69
caps.latest.revision: 7
ms.openlocfilehash: bf1d57447f9018f1535af14466427aaeabc048f3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369151"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a>View の Controls の ExpressionBinding の CustomControlName 要素 (書式)

コモンコントロールまたはビューコントロールの名前を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (形式) のコントロールの Customentries の CustomControlName (format) 式のバインド要素のビュー (format) の customentries 要素のためのコントロール用の CustomEntries 要素です。ビューのコントロール (Format) の式が Bindine の要素

## <a name="syntax"></a>構文

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomControlName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="text-value"></a>テキスト値

コントロールの名前を指定します。

## <a name="remarks"></a>コメント

書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。 次の要素は、これらのコントロールの名前を指定します。

- [構成用コントロールのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [ビューのコントロールに対する Control の Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[構成用コントロールのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[ビューのコントロールに対する Control の Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)

[ビューのコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
