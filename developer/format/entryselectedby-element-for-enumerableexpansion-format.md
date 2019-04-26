---
title: EnumerableExpansion (形式) の要素を EntrySelectedBy |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af6aff8-4c2d-4f08-9bb1-e1f3ed3e583e
caps.latest.revision: 11
ms.openlocfilehash: 6a371bdbb85d07730c32931a4a79ee40856ce298
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066211"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy 要素 (書式)

この定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。

構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EnumerableExpansion (形式)

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> この定義のコレクション オブジェクトの展開に必要な条件を定義します。|
|[EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> この定義のコレクション オブジェクトを展開する方法を使用する .NET 型のセットを指定します。|
|[EntrySelectedBy EnumerableExpansion (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> この定義のコレクション オブジェクトを展開する方法を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion 要素 (形式)](./enumerableexpansion-element-format.md)|ビューに表示されているときに、オブジェクトが展開されます、特定の .NET コレクションを定義します。|

## <a name="remarks"></a>コメント

少なくとも 1 つの型、選択範囲のセット、または定義のエントリの選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件を使用して、定義オブジェクトに特定のプロパティがある場合など、使用するのに必要な条件を定義または特定のプロパティの値またはスクリプトに評価される`true`します。 選択条件の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[データを表示するための条件を定義します。](./defining-conditions-for-displaying-data.md)

[EnumerableExpansion 要素 (形式)](./enumerableexpansion-element-format.md)

[EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[EntrySelectedBy EnumerableExpansion (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
