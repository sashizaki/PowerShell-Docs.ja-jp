---
title: ScriptBlock 要素の構成 (形式) のコントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb032dfc-9ef6-403c-b557-5858617e3483
caps.latest.revision: 6
ms.openlocfilehash: 102987970152420896a0c986f0973280ae209623
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853218"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy の構成 (形式) のコントロールの構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素構成 (形式) のコントロールの SelectionCondition の ScriptBlock 要素

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|使用する一般的なコントロールの定義を満たす必要がある条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
