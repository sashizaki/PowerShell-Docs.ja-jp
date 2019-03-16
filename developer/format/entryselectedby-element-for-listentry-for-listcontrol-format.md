---
title: ListControl (形式) の ListEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f7a74e9-764d-46ce-ab8e-8b9314ce1659
caps.latest.revision: 12
ms.openlocfilehash: 442565d25f60ae8e04501f3f9ffba35d486fbc8a
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054945"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a>ListControl の ListEntry の EntrySelectedBy 要素 (書式)

このリスト ビューの定義を使用する .NET 型または条件を使用するには、この定義が存在する必要がありますを定義します。 ほとんどの場合は、リスト ビューの 1 つだけ定義が必要です。 ただし、さまざまなオブジェクトのさまざまなデータを表示する同じリスト ビューを使用する場合は、リスト ビューの複数の定義を提供できます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntry の ListControl (形式) EntrySelectedBy 要素のListEntry ListControl (形式) の

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> このリスト ビューの定義を使用するのに必要な条件を定義します。|
|[ListControl (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> このリスト ビューの定義を使用して .NET 型のセットを指定します。|
|[EntrySelectedBy ListControl (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> このリスト ビューの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) の ListEntry 要素](./listentry-element-for-listcontrol-format.md)|一覧の行を表示する方法を定義します。|

## <a name="remarks"></a>コメント

少なくとも 1 つの型、選択範囲のセット、またはリスト ビューの定義の選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件を使用して、定義オブジェクトに特定のプロパティがある場合など、使用するのに必要な条件を定義または特定のプロパティの値またはスクリプトに評価される`true`します。 選択条件の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

## <a name="example"></a>例

次の例では、その .NET 型名を使用してリスト ビューのオブジェクトを定義する方法を示します。

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a>参照

[ListControl (形式) の ListEntry 要素](./listentry-element-for-listcontrol-format.md)

[ListControl (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[ListControl (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[EntrySelectedBy ListControl (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[リスト ビューの作成](./creating-a-list-view.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
