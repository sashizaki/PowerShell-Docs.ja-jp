---
title: 列挙 Able展開の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4126b799-c43d-4175-8513-6d761c65437e
caps.latest.revision: 9
ms.openlocfilehash: a51d8d22fa8b0c7f303a5e8f37edcc5e57724063
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368611"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。

Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙 Able膨張要素 (format) 列挙 able膨張拡張要素 (format) の Entryselectedby 要素の entryselectedby 要素の EntrySelectedBy 要素列挙 able膨張 (Format) の EntrySelectedBy の SelectionCondition に使用する EnumerableExpansion (Format) ScriptBlock 要素

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|この定義のコレクションオブジェクトを展開するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition の PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
