---
title: GroupBy (形式) の CustomEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066228"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a>GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)

このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。 少なくとも 1 つの型、選択範囲のセット、または定義の選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|省略可能な要素です。<br /><br /> この定義を使用するのに必要な条件を定義します。|
|[GroupBy (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|省略可能な要素です。<br /><br /> このコントロールの定義を使用して .NET 型のセットを指定します。|
|[GroupBy (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-groupby-format.md)|省略可能な要素です。<br /><br /> このコントロールの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) のカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

選択条件を使用して、使用する定義のオブジェクトに特定のプロパティがある場合などときや、特定のプロパティ値の条件が存在する必要がありますを定義またはスクリプトを評価する`true`します。 選択条件の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[GroupBy (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[GroupBy (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-groupby-format.md)

[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
