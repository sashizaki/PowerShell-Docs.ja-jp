---
title: GroupBy (形式) の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075870"
---
# <a name="propertyname-element-for-groupby-format"></a>GroupBy の PropertyName 要素 (書式)

その値が変更されるたびに、新しいグループを開始する .NET プロパティを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy (形式) のビュー (形式) PropertyName 要素の GroupBy 要素

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)|.NET オブジェクトのグループを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

.NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

Windows PowerShell は、このプロパティの値が変更されるたびに、新しいグループを開始します。

この要素が指定されている場合は指定できません、 [ScriptBlock](./scriptblock-element-for-groupby-format.md)要素を新しいグループを開始します。

## <a name="example"></a>例

次の例では、プロパティの値が変更されたときに、新しいグループを開始する方法を示します。

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

この要素を含む完全な書式設定ファイルの例は、次を参照してください。[表示幅が広い (GroupBy)](./wide-view-groupby.md)します。

## <a name="see-also"></a>参照

[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

[GroupBy (形式) の ScriptBlock 要素](./scriptblock-element-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
