---
title: PropertyName 要素 EntrySelectedBy WideEntry (形式) 用の SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340abb12-6df1-42f4-bdae-b0509c90952c
caps.latest.revision: 11
ms.openlocfilehash: 196877b97db9ed0592e357486c1318dc1e7efd31
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064681"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a>WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)

条件をトリガーする、.NET プロパティを指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy WideEntry (形式) のための WideEntry (形式) PropertyName 要素

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

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
|[WideEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|この定義を使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

少なくとも 1 つのプロパティ名またはスクリプトを評価する選択条件を指定する必要がありますが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[表示幅が広い](./creating-a-wide-view.md)します。

## <a name="see-also"></a>参照

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[SelectionCondition EntrySelectedBy WideEntry (形式) のためのスクリプト ブロックの要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
