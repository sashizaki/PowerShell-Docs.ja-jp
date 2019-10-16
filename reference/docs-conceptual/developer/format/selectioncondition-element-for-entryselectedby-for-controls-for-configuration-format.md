---
title: 構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368451"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)

共通のコントロール定義を使用するために必要な条件を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素の構成 (書式設定) 要素構成 (Format) CustomEntry 要素の CustomControl のためのコントロール用の構成 (形式) の構成 (形式) のために、customentry に対して EntrySelectedBy の Configuration (Format) SelectionCondition 要素を指定します。構成 (形式)

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

次のセクションでは、属性、子要素、`SelectionCondition` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[構成用のコントロールの SelectionCondition の PropertyName 要素 (形式)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[構成用のコントロールの SelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[構成用のコントロールの SelectionCondition の SelectionSetName 要素 (形式)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[構成用のコントロールの SelectionCondition の TypeName 要素 (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration 用のコントロール用の CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|コモンコントロール定義のこのエントリを使用する .NET 型を定義します。|

## <a name="remarks"></a>コメント

選択条件を定義するときは、次のガイドラインに従う必要があります。

- 選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。

選択条件を使用する方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[構成用のコントロールの SelectionCondition の PropertyName 要素 (形式)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成用のコントロールの SelectionCondition の ScriptBlock 要素 (形式)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成用のコントロールの SelectionCondition の SelectionSetName 要素 (形式)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成用のコントロールの SelectionCondition の TypeName 要素 (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Configuration 用のコントロール用の CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
