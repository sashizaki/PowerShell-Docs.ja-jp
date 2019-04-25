---
title: PropertyName 要素 EntrySelectedBy ListControl (形式) 用の SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: 7d526372cf80327b3fb9b79b6e83429c57780183
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064893"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)

条件をトリガーする、.NET プロパティを指定します。 このプロパティが存在するかを評価すると`true`条件が満たされ、一覧のエントリを使用します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy ListEntry (形式) のための ListEntry (形式) PropertyName 要素

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
|[ListEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|このリストのエントリを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET プロパティの名前を指定します。

## <a name="remarks"></a>コメント

選択条件では、少なくとも 1 つのプロパティの名前またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。

リスト ビューの他のコンポーネントに関する詳細については、次を参照してください。[リスト ビューの作成](./creating-a-list-view.md)です。

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[ときにデータの条件の定義が表示されます。](./defining-conditions-for-displaying-data.md)

[ListEntry 要素 (形式)](./listentry-element-for-listcontrol-format.md)

[SelectionCondition EntrySelectedBy ListEntry (形式) のためのスクリプト ブロックの要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
