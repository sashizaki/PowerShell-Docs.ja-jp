---
title: GroupBy (Format) の Label 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365201"
---
# <a name="label-element-for-groupby-format"></a>GroupBy の Label 要素 (書式)

新しいグループが検出されたときに表示されるラベルを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby のビュー (format) Label 要素の groupby (形式)

## <a name="syntax"></a>構文

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Label` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)|オブジェクトの新しいグループをどのように表示するかを定義します。|

## <a name="text-value"></a>テキスト値

Windows PowerShell で新しいプロパティまたはスクリプト値が検出されたときに表示されるテキストを指定します。

## <a name="remarks"></a>コメント

Windows PowerShell では、この要素で指定されたテキストに加えて、グループを開始する新しい値が表示され、グループの前後に空白行が追加されます。

## <a name="example"></a>例

次の例は、新しいグループのラベルを示しています。 表示されるラベルは次のようになります: `Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。

## <a name="see-also"></a>参照

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
