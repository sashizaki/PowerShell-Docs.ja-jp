---
title: GroupBy (Format) の EntrySelectedBy の SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569c623-2277-49e3-933e-c26262b91cd5
caps.latest.revision: 6
ms.openlocfilehash: 69cd113c444b4e3c5dceabcdfddb439cd1376f6b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364741"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a>GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)

リストエントリの一連の .NET オブジェクトを指定します。 エントリに指定できる選択セットの数に制限はありません。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl に対して、CustomEntry for groupby (format) の SelectionSetName 要素を指定します。 groupby (形式) に対して EntrySelectedBy の要素を指定します。

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-customentry-for-groupby-format.md)|このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

各カスタムコントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。 たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。 選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。

カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。

## <a name="see-also"></a>参照

[GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[カスタムコントロールの作成](./creating-custom-controls.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
