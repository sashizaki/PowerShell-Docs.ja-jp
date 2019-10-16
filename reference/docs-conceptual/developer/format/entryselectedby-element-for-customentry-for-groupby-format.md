---
title: GroupBy (Format) の CustomEntry の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363861"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a>GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)

このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl には、GroupBy (形式) の CustomEntry の要素のエントリがあります。

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。 定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|省略可能な要素。<br /><br /> この定義を使用するために必要な条件を定義します。|
|[GroupBy (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|省略可能な要素。<br /><br /> コントロールのこの定義を使用する .NET 型のセットを指定します。|
|[GroupBy (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-groupby-format.md)|省略可能な要素。<br /><br /> コントロールのこの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomControl の CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

選択条件を使用して、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true` に評価される場合など、使用する定義に存在する必要がある条件を定義します。 選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[GroupBy (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[GroupBy (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-groupby-format.md)

[ビューのコントロール (Format) の CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
