---
title: ビュー (Format) のコントロールに対する CustomEntry の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363891"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a>View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)

このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビューのための CustomControl (format) CustomEntry 要素のコントロール用のカスタムエントリのためのコントロールのためのコントロールのための、CustomEntry for Controls for コントロールの EntrySelectedBy 要素

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
|[ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> この定義を使用するために必要な条件を定義します。|
|[ビューのコントロール (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> コントロールのこの定義を使用する .NET 型のセットを指定します。|
|[ビューのコントロール (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> コントロールのこの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロール (Format) の CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

選択条件を使用して、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true` に評価される場合など、使用する定義に存在する必要がある条件を定義します。 選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[ビューのコントロール (Format) の CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
