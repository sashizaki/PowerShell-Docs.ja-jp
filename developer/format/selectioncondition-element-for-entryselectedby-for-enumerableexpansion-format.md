---
title: EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064137"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)

この定義のコレクション オブジェクトの展開に必要な条件を定義します。

構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EntrySelectedBy の EnumerableExpansion (形式) SelectionCondition 要素EnumerableExpansion (形式)

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
|[SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のための PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする、.NET プロパティを指定します。|
|[SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のためのスクリプト ブロックの要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のための TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)|.NET コレクション オブジェクトの拡張機能では、この定義を定義します。|

## <a name="remarks"></a>コメント

各定義に少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。

選択条件を定義している場合は、次の要件が適用されます。

- 選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。

選択条件を使用する方法の詳細については、次を参照してください。 [Diplaying データの条件を定義する](./defining-conditions-for-displaying-data.md)します。

ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[表示幅が広い](./creating-a-wide-view.md)します。

## <a name="see-also"></a>参照

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
