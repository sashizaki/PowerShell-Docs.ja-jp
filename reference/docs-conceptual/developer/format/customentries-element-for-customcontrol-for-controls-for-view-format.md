---
title: View (Format) 用のコントロールの CustomControl の CustomEntries 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3485958a-ba87-4932-907c-a8f140c4abdb
caps.latest.revision: 8
ms.openlocfilehash: 4856aee930285781a101868bd6cb67824585bce1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368811"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>View の Controls の CustomControl の CustomEntries 要素 (書式)

コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビューのコントロールの CustomControl (形式)

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

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロール (Format) の CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)|必須の要素です。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View (Format) コントロールのコントロールの CustomControl 要素](./customcontrol-element-for-control-for-controls-for-view-format.md)|ビューによって使用されるコントロールを定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、コントロールの定義は1つだけであり、1つの @no__t 0 要素で指定されます。 ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。 そのような場合は、オブジェクトまたはオブジェクトのセットごとに `CustomEntry` 要素を定義できます。

## <a name="see-also"></a>参照

[ビューのコントロール (Format) の CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[View (Format) コントロールのコントロールの CustomControl 要素](./customcontrol-element-for-control-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
