---
title: GroupBy (形式) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e01344bd-ad69-4789-8e9f-2e79880c3a33
caps.latest.revision: 6
ms.openlocfilehash: cb79fb942111cee89c6b2abba75de4c494082b7e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064343"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a>GroupBy の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の SelectionCondition の GroupBy (形式) ScriptBlock 要素 EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|コントロールの定義を使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
