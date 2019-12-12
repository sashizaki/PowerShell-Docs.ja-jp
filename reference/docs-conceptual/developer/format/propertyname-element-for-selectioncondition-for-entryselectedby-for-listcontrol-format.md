---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: 7d526372cf80327b3fb9b79b6e83429c57780183
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362291"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、リストエントリが使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリEntryselectedby for ListEntry (Format) PropertyName Element for EntrySelectedBy for ListEntry (Format)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|このリストエントリが使用されるために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET プロパティ名を指定します。

## <a name="remarks"></a>コメント

選択条件では、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。

## <a name="see-also"></a>参照

[リストビューの作成](./creating-a-list-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[ListEntry 要素 (Format)](./listentry-element-for-listcontrol-format.md)

[ListEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
