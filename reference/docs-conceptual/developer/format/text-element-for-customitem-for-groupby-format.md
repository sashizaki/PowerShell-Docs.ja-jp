---
title: GroupBy (Format) の CustomItem のテキスト要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 811dc3a6f83f93513bd8380a7c3b66a813fe7801
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783366"
---
# <a name="text-element-for-customitem-for-groupby-format"></a>GroupBy の CustomItem の Text 要素 (書式)

ラベル、データを囲む角かっこ、データをインデントするスペースなど、コントロールによって表示されるデータに追加されるテキストを指定します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素については、groupby (形式) の CustomControl 要素を使用して、groupby (形式) に対して、groupby (形式) の Custommentry 要素に対して、CustomControl for groupby (format) の Custommentry 要素を指定します。

## <a name="syntax"></a>構文

```xml
<Text>TextToDisplay</Text>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `Text` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy の CustomEntry の CustomItem 要素 (書式)](./customitem-element-for-customentry-for-groupby-format.md)|カスタムコントロールビューのコントロールを定義します。|

## <a name="text-value"></a>テキスト値

表示するデータのコントロールのテキストを指定します。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[GroupBy の CustomEntry の CustomItem 要素 (書式)](./customitem-element-for-customentry-for-groupby-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
