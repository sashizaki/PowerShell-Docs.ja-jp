---
title: TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ae4d6b-dc95-4a1d-8e32-31ff084a951f
caps.latest.revision: 10
ms.openlocfilehash: edb163f2b0b5129bd741677dce882888d9bbfd89
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361921"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)

条件をトリガーする .NET 型のセットを指定します。 このセット内のいずれかの型が存在する場合、条件が満たされ、テーブルビューのこの定義を使用してオブジェクトが表示されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の要素TableRowEntry (format) 用の EntrySelectedBy for TableRowEntry (Format) の SelectionSetName 要素の selectioncondition 要素を指定します。

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|テーブルビューのこの定義に使用する必要がある条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。 選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

ワイドビューのその他のコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
