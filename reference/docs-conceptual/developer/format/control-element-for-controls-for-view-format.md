---
title: ビューのコントロールの Control 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363471"
---
# <a name="control-element-for-controls-for-view--format"></a>View の Controls の Control 要素 (書式)

ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロール要素 (形式)

## <a name="syntax"></a>構文

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Control` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)|必須の要素です。<br /><br /> コントロールの名前を指定します。|
|[View (Format) コントロールのコントロールの CustomControl 要素](./customcontrol-element-for-control-for-controls-for-view-format.md)|必須の要素です。<br /><br /> このビューによって使用されるコントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Controls 要素 (Format)](./controls-element-for-view-format.md)|特定のビューで使用できるビューコントロールを定義します。|

## <a name="remarks"></a>コメント

このコントロールは、次の要素によって指定できます。

- [ビューのコントロール (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [CustomControl for View (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [GroupBy (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [GroupBy (Format) の CustomControlName 要素](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>参照

[View (Format) コントロールのコントロールの CustomControl 要素](./customcontrol-element-for-control-for-controls-for-view-format.md)

[ビューのコントロール (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[CustomControl for View (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[GroupBy (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (Format) の式のバインドの CustomControlName 要素](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Controls 要素 (Format)](./controls-element-for-view-format.md)

[ビューのコントロールに対する Control の Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
