---
title: WideEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13a429c-a31b-4e29-828c-c0c0917b5415
caps.latest.revision: 11
ms.openlocfilehash: baea89e4b259611dfa45b6bcf94fa0bf2df6b9de
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368411"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a>WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)

条件をトリガーする .NET 型のセットを指定します。 このセット内のいずれかの型が存在する場合、条件が満たされ、このワイドビューの定義を使用してオブジェクトが表示されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionCondition 要素の (Format) 項目の EntrySelectedBy 要素WideEntry (format) の EntrySelectedBy for WideEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素

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
|[WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|この定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。 選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="see-also"></a>参照

[ワイドビューの作成](./creating-a-wide-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[選択セットの定義](./defining-selection-sets.md)

[WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
