---
title: ビュー (Format) のコントロールの式のバインドの ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 42946ed9f3241912366192b2ab2fdfb8f8582d83
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785491"
---
# <a name="scriptblock-element-for-expressionbinding-for-controls-for-view-format"></a>View の Controls の ExpressionBinding の ScriptBlock 要素 (書式)

コントロールによって値が表示されるスクリプトを指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (形式) コントロールのコントロールの要素 (形式) コントロールの要素 (書式) を制御するためのコントロールの CustomControl 要素 (format) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロールの CustomEntries を使用して、ビュー (形式) の Customentries 要素を表示するためのコントロールに対して、ビュー (format) の式のバインド要素を表示するコントロールの式のバインドのバインド要素を指定します。

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View の Controls の CustomItem の ExpressionBinding 要素 (書式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|コントロールによって表示されるデータを定義します。|

## <a name="text-value"></a>テキスト値

コントロールによって値が表示されるスクリプトを指定します。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[View の Controls の CustomItem の ExpressionBinding 要素 (書式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
