---
title: GroupBy (形式) の要素にラベルを付ける |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065412"
---
# <a name="label-element-for-groupby-format"></a>GroupBy の Label 要素 (書式)

新しいグループが発生したときに表示されるラベルを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) の GroupBy (形式) のビュー (形式) ラベル要素の GroupBy 要素

## <a name="syntax"></a>構文

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Label`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)|オブジェクトの新しいグループを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

Windows PowerShell が新しいプロパティまたはスクリプトの値を検出するたびに表示されるテキストを指定します。

## <a name="remarks"></a>コメント

この要素で指定されたテキスト、だけでなく Windows PowerShell には、グループを開始し、グループの前後に空白行を追加した新しい値が表示されます。

## <a name="example"></a>例

次の例では、新しいグループのラベルを示します。 表示されるラベルは、次のようになります。 `Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

この要素を含む完全な書式設定ファイルの例は、次を参照してください。[表示幅が広い (GroupBy)](./wide-view-groupby.md)します。

## <a name="see-also"></a>参照

[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
