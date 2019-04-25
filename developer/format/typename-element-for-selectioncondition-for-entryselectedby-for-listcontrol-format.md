---
title: SelectionCondition EntrySelectedBy ListControl (形式) のための TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd025a3a-3780-40db-a068-873e7df38015
caps.latest.revision: 9
ms.openlocfilehash: 2b76b040b39088cc9c3b9d6890c38df3c533b39f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083860"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この型が存在するときに、一覧のエントリが使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries の ListControl (形式) EntrySelectedBy 要素のListEntry SelectionCondition EntrySelectedBy ListControl (形式) のための ListControl (形式) の TypeName 要素 EntrySelectedBy の ListControl (形式) SelectionCondition 要素

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|このリストのエントリを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。

## <a name="remarks"></a>コメント

選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

その他の詳細については、リスト ビューのコンポーネントを参照してください[リスト ビューを作成する](./creating-a-list-view.md)します。

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[ListControl (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
