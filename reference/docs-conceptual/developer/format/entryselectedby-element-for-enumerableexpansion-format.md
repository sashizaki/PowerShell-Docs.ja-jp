---
title: 列挙 Able膨張 (Format) の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af6aff8-4c2d-4f08-9bb1-e1f3ed3e583e
caps.latest.revision: 11
ms.openlocfilehash: 6a371bdbb85d07730c32931a4a79ee40856ce298
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368801"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy 要素 (書式)

この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。

Configuration 要素 (Format) DefaultSettings 要素 (format) の列挙 Able膨張要素 (format) 列挙 Able膨張の要素 (形式) には、列挙 Able拡張 (Format) の要素を指定します。

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> この定義のコレクションオブジェクトを展開するために必要な条件を定義します。|
|[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> コレクションオブジェクトの展開方法のこの定義を使用する一連の .NET 型を指定します。|
|[列挙型展開の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> コレクションオブジェクトの展開方法のこの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開要素 (形式)](./enumerableexpansion-element-format.md)|特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。|

## <a name="remarks"></a>コメント

定義エントリには、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件を使用して、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true`として評価される場合など、使用する定義に存在する必要がある条件を定義します。 選択条件の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)

[列挙 Able展開要素 (形式)](./enumerableexpansion-element-format.md)

[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[列挙型展開の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
