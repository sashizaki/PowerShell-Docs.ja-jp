---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368591"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトが `true`に評価されると、条件が満たされ、リストエントリが使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリEntryselectedby for ListEntry (Format) の SelectionCondition に使用する EntrySelectedBy for ListEntry (Format) ScriptBlock 要素

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|このリストエントリが使用されるために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。 (選択条件を使用する方法の詳細については、「[ビューエントリまたはアイテムが使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください)。

リストビューのその他のコンポーネントの詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。

## <a name="see-also"></a>参照

[ListEntry 要素 (Format)](./listentry-element-for-listcontrol-format.md)

[ListEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[リスト ビュー](./creating-a-list-view.md)

[ビューエントリまたはアイテムが使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
