---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362051"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a>View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)

コントロール定義を使用するために必要な条件を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロールの CustomControl (書式) の CustomEntry 要素のコントロール用のカスタムエントリのためのコントロールのためのコントロールのためのコントロールのためのコントロールのための、ビューのコントロールの EntrySelectedBy の SelectionCondition 要素を表示するためのコントロール (形式

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
|[ビューのコントロールの SelectionCondition の PropertyName 要素 (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[ビューのコントロールの SelectionCondition の ScriptBlock 要素 (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[ビューのコントロール (Format) の SelectionCondition の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[ビューのコントロールの SelectionCondition の TypeName 要素 (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロールに対する CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="remarks"></a>コメント

選択条件を定義する場合は、次の要件が適用されます。

- 選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。

選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[ビューのコントロールの SelectionCondition の PropertyName 要素 (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[ビューのコントロールの SelectionCondition の ScriptBlock 要素 (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[ビューのコントロール (Format) の SelectionCondition の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[ビューのコントロールの SelectionCondition の TypeName 要素 (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[ビューのコントロールに対する CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
