---
title: 列挙 Able膨張 (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362011"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)

この定義のコレクションオブジェクトを展開するために必要な条件を定義します。

Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙 Able膨張要素 (format) 列挙 able膨張拡張要素 (format) の Entryselectedby 要素の entryselectedby 要素の EntrySelectedBy 要素列挙 Able展開 (形式)

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

次のセクションでは、属性、子要素、`SelectionCondition` 要素の親要素について説明します。 1つの `PropertyName` または `ScriptBlock` の要素を指定する必要があります。 @No__t-0 および `TypeName` の要素は省略可能です。 いずれかの要素を指定できます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition の PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[列挙 Able展開の EntrySelectedBy の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[列挙 Able膨張 (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[列挙型拡張の EntrySelectedBy の SelectionCondition の TypeName 要素 (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開 (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)|この定義によって展開される .NET コレクションオブジェクトを定義します。|

## <a name="remarks"></a>コメント

各定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

選択条件を定義する場合は、次の要件が適用されます。

- 選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。

選択条件の使用方法の詳細については、「[データの Diplaying の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。

## <a name="see-also"></a>参照

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
