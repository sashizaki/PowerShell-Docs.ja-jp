---
title: GroupBy (Format) の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362521"
---
# <a name="propertyname-element-for-groupby-format"></a>GroupBy の PropertyName 要素 (書式)

値が変更されるたびに新しいグループを開始する .NET プロパティを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (書式) GroupBy 要素 (形式) の PropertyName 要素

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)|.NET オブジェクトのグループを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

.NET プロパティ名を指定します。

## <a name="remarks"></a>コメント

このプロパティの値が変更されるたびに、Windows PowerShell によって新しいグループが開始されます。

この要素が指定されている場合、 [ScriptBlock](./scriptblock-element-for-groupby-format.md)要素を指定して新しいグループを開始することはできません。

## <a name="example"></a>例

次の例は、プロパティの値が変更されたときに新しいグループを開始する方法を示しています。

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。

## <a name="see-also"></a>参照

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[GroupBy (Format) の ScriptBlock 要素](./scriptblock-element-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
