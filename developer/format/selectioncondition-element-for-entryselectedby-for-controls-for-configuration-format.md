---
title: 構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854148"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)

使用する一般的なコントロールの定義を満たす必要がある条件を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

コントロールのコントロールのカスタム コントロールの構成 (形式) CustomEntries 要素の構成 (形式) のカスタム コントロール要素のコントロールの構成 (形式) のコントロール要素の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy CustomEntry のための構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの構成 (形式) CustomEntry 要素構成 (形式)

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
|[構成 (形式) のコントロールの SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[構成 (形式) のコントロールの SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[構成 (形式) のコントロールの SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|このエントリの一般的なコントロールの定義を使用する .NET 型を定義します。|

## <a name="remarks"></a>コメント

選択条件を定義するときに、次のガイドラインに従ってください。

- 選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。

選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの SelectionCondition PropertyName 要素](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
