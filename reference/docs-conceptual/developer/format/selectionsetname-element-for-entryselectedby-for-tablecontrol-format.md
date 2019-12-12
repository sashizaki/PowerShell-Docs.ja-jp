---
title: TableControl (Format) の EntrySelectedBy の SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368321"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a>TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)

テーブルビューのこのエントリを使用する .NET 型のセットを指定します。 エントリに指定できる選択セットの数に制限はありません。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) SelectionSetName Element By Element (Format) 要素TableRowEntry の EntrySelectedBy (形式)

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性と要素

以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|このエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。 たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。 選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。

エントリの選択セットを指定する場合、型名を指定することはできません。 .NET 型を指定する方法の詳細については、「 [TableRowEntry (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-tablecontrol-format.md)」を参照してください。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="see-also"></a>参照

[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[ビューに対するオブジェクトのセットの定義](./defining-selection-sets.md)

[テーブルビューの作成](./creating-a-table-view.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
