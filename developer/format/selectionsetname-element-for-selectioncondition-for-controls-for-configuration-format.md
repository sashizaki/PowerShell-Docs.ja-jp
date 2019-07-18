---
title: 構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7dcaeadb-4e79-47a0-96e2-8952af26abbe
caps.latest.revision: 7
ms.openlocfilehash: 5db35a8094ea2bb966c8d6a96802c72f64c05c17
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064025"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)

条件をトリガーする .NET 型のセットを指定します。 このセット内の型のいずれかが存在して、条件が満たされると、このコントロールを使用して、オブジェクトが表示されます。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

コントロールのコントロールのカスタム コントロールの構成 (形式) CustomEntries 要素の構成 (形式) のカスタム コントロール要素のコントロールの構成 (形式) のコントロール要素の構成要素 (形式) のコントロール要素CustomEntry controls for EntrySelectedBy の構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの構成 (形式) CustomEntry 要素構成 (形式) のコントロールの SelectionCondition の構成 (形式) SelectionSetName 要素

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
|[構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|コントロールの定義を使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。 作成と選択範囲のセットの参照の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。

選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
