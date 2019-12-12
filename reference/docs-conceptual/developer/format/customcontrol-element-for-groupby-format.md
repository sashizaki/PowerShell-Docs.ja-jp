---
title: GroupBy (Format) の CustomControl 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2472e256-8f4f-4288-8b67-a3300649dafa
caps.latest.revision: 9
ms.openlocfilehash: 2e84e770a345e272d4c5917b00afe7520840e1db
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368961"
---
# <a name="customcontrol-element-for-groupby-format"></a>GroupBy の CustomControl 要素 (書式)

新しいグループを表示するカスタムコントロールを定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby 要素 (format) の CustomControl 要素を指定します。

## <a name="syntax"></a>構文

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomControl` 要素の属性、子要素、および親要素について説明します。 任意の数の子要素を指定し、任意の順序で一覧表示することができます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomControl の CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)|必須の要素です。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)|Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[GroupBy (Format) の CustomControl の CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
