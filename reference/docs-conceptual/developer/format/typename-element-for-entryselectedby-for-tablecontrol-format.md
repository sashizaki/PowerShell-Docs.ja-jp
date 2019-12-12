---
title: TableControl の EntrySelectedBy の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd872ada-d476-4c4d-a788-ccac3f983070
caps.latest.revision: 10
ms.openlocfilehash: 7bbb47268a23fcb37a34e2287a6ce949313a13bb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361631"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a>TableControl の EntrySelectedBy の TypeName 要素 (書式)

テーブルビューのこのエントリを使用する .NET 型を指定します。 テーブルエントリに指定できる型の数に制限はありません。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) EntrySelectedBy Element (Format) の TypeName 要素TableRowEntry の場合 (形式)

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
|[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|このエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の名前を指定します。

## <a name="remarks"></a>コメント

各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
