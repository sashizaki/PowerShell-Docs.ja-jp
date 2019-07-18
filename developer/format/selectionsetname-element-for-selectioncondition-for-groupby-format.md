---
title: GroupBy (形式) の SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9a4912-d755-42f3-8058-53c0797e28e4
caps.latest.revision: 6
ms.openlocfilehash: 371913eda2b09ff6788494b68738f2ad53ccb115
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063768"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a>GroupBy の SelectionCondition の SelectionSetName 要素 (書式)

条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、このコントロールを使用して、オブジェクトが表示されます。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の SelectionCondition の GroupBy (形式) SelectionSetName 要素 EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|コントロールの定義を使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。 作成と選択範囲のセットの参照の詳細については、次を参照してください。[選択範囲の設定を定義する](./defining-selection-sets.md)します。

この要素が指定されている場合は指定できません、 [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md)要素。 選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[GroupBy (形式) の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-groupby-format.md)

[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
