---
title: TableControl (形式) の EntrySelectedBy の SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ae4d6b-dc95-4a1d-8e32-31ff084a951f
caps.latest.revision: 10
ms.openlocfilehash: edb163f2b0b5129bd741677dce882888d9bbfd89
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064052"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)

条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、テーブル ビューのこの定義を使用して、オブジェクトが表示されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素を TableRowEntry (形式)SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TableRowEntry (形式) SelectionSetName 要素 EntrySelectedBy SelectionCondition 要素

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|テーブル ビューのこの定義に使用する必要があります条件を定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。 作成と選択範囲のセットの参照の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。

ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
