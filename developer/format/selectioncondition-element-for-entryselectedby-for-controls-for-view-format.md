---
title: コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064235"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a>View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)

コントロールの定義を使用するのに必要な条件を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry EntrySelectedBy のビュー (コントロールのビュー (形式) SelectionCondition 要素のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロール形式)

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

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[コントロールが表示されます (形式) の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[コントロールが表示されます (形式) の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。|

## <a name="remarks"></a>コメント

選択条件を定義している場合は、次の要件が適用されます。

- 選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。

選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
