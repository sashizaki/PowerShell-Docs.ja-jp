---
title: CustomEntry for CustomControl for View (Format) の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368781"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a>View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)

このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (format) EntrySelectedBy 要素 for view (Format) EntrySelectedByCustomEntry for ビューの要素 (形式)

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
|[CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|省略可能な要素。<br /><br /> この定義を使用するために必要な条件を定義します。|
|[CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|省略可能な要素。<br /><br /> コントロールビューのこの定義を使用する .NET 型のセットを指定します。|
|[CustomEntry (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|省略可能な要素。<br /><br /> コントロールビューのこの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View (Format) の CustomEntries の CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|特定の .NET オブジェクトで使用されるコントロールを定義します。|

## <a name="remarks"></a>コメント

エントリの種類、選択セット、または選択条件を少なくとも1つ指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true` に評価される場合など、エントリを使用するために存在する必要がある条件を定義するために使用されます。 選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールビュー](./creating-custom-controls.md)」を参照してください。

## <a name="see-also"></a>参照

[CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[CustomEntry (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[View (Format) の CustomEntries の CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[カスタムコントロールビュー](./creating-custom-controls.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
