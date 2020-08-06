---
title: ビューのコントロールの Control 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783808"
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

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `Control` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ビューのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)|必須の要素です。<br /><br /> コントロールの名前を指定します。|
|[View の Controls の Control の CustomControl 要素 (書式)](./customcontrol-element-for-control-for-controls-for-view-format.md)|必須の要素です。<br /><br /> このビューによって使用されるコントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Controls 要素 (Format)](./controls-element-for-view-format.md)|特定のビューで使用できるビューコントロールを定義します。|

## <a name="remarks"></a>解説

このコントロールは、次の要素によって指定できます。

- [View の Controls の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [GroupBy の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [GroupBy の CustomControlName 要素 (書式)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>参照

[View の Controls の Control の CustomControl 要素 (書式)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[View の Controls の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[GroupBy の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[GroupBy の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Controls 要素 (Format)](./controls-element-for-view-format.md)

[View の Controls の Control の Name 要素 (書式)](./name-element-for-control-for-controls-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
