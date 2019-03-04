---
title: ListControl (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff7763c-5ce0-49c1-a480-1249c9f57a13
caps.latest.revision: 11
ms.openlocfilehash: 7fd431b4b1ddecd3a7358c2bf97f299b97162b34
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860158"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)

.NET オブジェクト、リストのエントリのセットを指定します。 エントリに指定できる選択セットの数に制限はありません。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionSetName 要素EntrySelectedBy ListEntry (形式) の

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|このリストのエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

リストの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。

複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。 たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。 選択範囲のセットを定義する詳細については、次を参照してください。[ビューのオブジェクトのセットを定義する](./defining-selection-sets.md)します。

リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

## <a name="example"></a>例

次の例では、選択リスト ビューのエントリのセットを指定する方法を示します。

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[ListEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
