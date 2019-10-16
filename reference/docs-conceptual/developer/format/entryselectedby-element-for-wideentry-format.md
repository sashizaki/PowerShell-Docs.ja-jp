---
title: WideEntry の EntrySelectedBy 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363331"
---
# <a name="entryselectedby-element-for-wideentry-format"></a>WideEntry の EntrySelectedBy 要素 (書式)

ワイドビューのこの定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) の要素 (format)

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`EntrySelectedBy` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|省略可能な要素。<br /><br /> このワイドビュー定義を使用するために必要な条件を定義します。|
|[WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|省略可能な要素。<br /><br /> このワイドビュー定義を使用する一連の .NET 型を指定します。|
|[WideEntry (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-wideentry-format.md)|省略可能な要素。<br /><br /> このワイドビュー定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)|ワイドビューの定義を提供します。|

## <a name="remarks"></a>コメント

ワイドビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプト値が `true` に評価される場合など、使用する定義に必要な条件を定義するために使用されます。 選択条件の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="see-also"></a>参照

[WideEntry 要素 (Format)](./wideentry-element-for-widecontrol-format.md)

[WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-wideentry-format.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
