---
title: ListEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae67e47-6c60-4741-8430-78d2cb6067b1
caps.latest.revision: 10
ms.openlocfilehash: ccfc0b772ad3b2d1979c7c832a5153de870035d7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368401"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a>ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)

条件をトリガーする .NET 型のセットを指定します。 このセット内のいずれかの型が存在する場合、条件が満たされ、リストビューのこの定義を使用してオブジェクトが表示されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリListEntry (format) の EntrySelectedBy for ListEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素

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
|[ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|リストビューのこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。 選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。

## <a name="see-also"></a>参照

[リストビューの作成](./creating-a-list-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
