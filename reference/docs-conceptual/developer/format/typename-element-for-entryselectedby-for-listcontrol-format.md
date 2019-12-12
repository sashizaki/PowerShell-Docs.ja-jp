---
title: ListControl (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7345c-b808-4c1e-bd54-cb870b407432
caps.latest.revision: 14
ms.openlocfilehash: 0f7216d4dcc0380bceb47ea7c15b3d4a7e5ceeb2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361661"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の TypeName 要素 (書式)

リストビューのこのエントリを使用する .NET 型を指定します。 リストエントリに指定できる型の数に制限はありません。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) TypeName 要素の (format) EntrySelectedBy ElementListControl の EntrySelectedBy (形式)

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|このリストエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。|

## <a name="text-value"></a>テキスト値

`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

リストビューでのこの要素の使用方法の詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。

## <a name="example"></a>例

次の例では、リストビューのエントリの選択セットを指定する方法を示します。

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>参照

[リストビューの作成](./creating-a-list-view.md)

[ListEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
