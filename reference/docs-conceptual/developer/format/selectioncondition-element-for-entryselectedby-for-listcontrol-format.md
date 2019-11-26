---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7649d5d0-2b56-49b5-a670-dde46caca343
caps.latest.revision: 11
ms.openlocfilehash: 7150b29ad84dfb587215ee3e64c356adbd5a6305
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417542"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)

リストビューのこの定義を使用するために必要な条件を定義します。 リスト定義に指定できる選択条件の数に制限はありません。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリListEntry の EntrySelectedBy (形式)

## <a name="syntax"></a>構文

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、`SelectionCondition` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[ListEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[EntrySelectedBy for ListEntry (Format) の SelectionCondition の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[ListEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableRowEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|このテーブルエントリを使用する .NET 型、またはこのエントリを使用するために必要な条件を定義します。|

## <a name="remarks"></a>コメント

選択条件を定義する場合は、次の要件が適用されます。

- 選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。

選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。

## <a name="see-also"></a>関連項目

[リストビューの作成](./creating-a-list-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[ListEntry 要素 (Format)](./listentry-element-for-listcontrol-format.md)

[ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[ListEntry (Format) の EntrySelectedBy の TypeName 要素](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
