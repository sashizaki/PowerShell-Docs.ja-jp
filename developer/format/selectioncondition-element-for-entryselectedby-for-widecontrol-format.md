---
title: WideControl (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7a9f086-b1ca-4400-9be7-9ec1ec8880f3
caps.latest.revision: 11
ms.openlocfilehash: f20679e3392b99a049c075f24c7712262bab08e1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063996"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a>WideControl の EntrySelectedBy の SelectionCondition 要素 (書式)

この定義を使用するのに必要な条件を定義します。 ワイド エントリの定義に指定できる選択条件の数に制限はありません。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionCondition 要素EntrySelectedBy WideEntry (形式) の

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

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。 1 つを指定する必要があります`PropertyName`または`ScriptBlock`要素。 `SelectionSetName`と`TypeName`要素は省略可能です。 要素のいずれかのいずれかを指定できます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[SelectionCondition EntrySelectedBy WideEntry (形式) のための PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[SelectionCondition EntrySelectedBy WideEntry (形式) のためのスクリプト ブロックの要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプト ブロックを指定します。|
|[EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[SelectionCondition EntrySelectedBy WideEntry (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-wideentry-format.md)|このワイド エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。|

## <a name="remarks"></a>コメント

少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている各ワイド エントリが必要です。

選択条件を定義している場合は、次の要件が適用されます。

- 選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。

選択条件を使用する方法の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。

ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。

## <a name="see-also"></a>参照

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[WideEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-wideentry-format.md)

[SelectionCondition EntrySelectedBy WideEntry (形式) のための PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[SelectionCondition EntrySelectedBy WideEntry (形式) のためのスクリプト ブロックの要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[SelectionCondition EntrySelectedBy WideEntry (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
