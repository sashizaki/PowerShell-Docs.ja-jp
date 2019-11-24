---
title: GroupBy (Format) の CustomControl の CustomEntries 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364091"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a>GroupBy の CustomControl の CustomEntries 要素 (書式)

コントロールの定義を提供します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー Element (format) GroupBy 要素の groupby (format) CustomControl 要素を groupby (形式) の CustomControl の CustomEntries 要素に設定します。

## <a name="syntax"></a>構文

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomEntries` 要素の属性、子要素、および親要素について説明します。 指定できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (Format) の CustomControl の CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)|必須の要素です。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (Format) の CustomControl 要素](./customcontrol-element-for-groupby-format.md)|新しいグループを表示するカスタムコントロールを定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、コントロールの定義は1つだけであり、1つの `CustomEntry` 要素で指定されます。 ただし、同じコントロールを使用して異なるグループを表示する場合は、複数の定義を指定できます。 そのような場合は、グループの `CustomEntry` 要素を定義できます。

## <a name="see-also"></a>関連項目

[ビューのコントロール (Format) の CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[GroupBy (Format) の CustomControl 要素](./customcontrol-element-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
