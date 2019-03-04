---
title: GroupBy (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855168"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a>GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)

コントロールの定義が使用するのに必要な条件を定義します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール

## <a name="syntax"></a>構文

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[GroupBy (形式) の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[GroupBy (形式) の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[GroupBy (形式) の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-groupby-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-groupby-format.md)|このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。|

## <a name="remarks"></a>コメント

選択条件を定義している場合は、次の要件が適用されます。

- 選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。

選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールの SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[ビュー (形式) のカスタム コントロールの SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[ビュー (形式) 用のカスタム コントロールの SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[GroupBy (形式) の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-groupby-format.md)

[GroupBy (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
