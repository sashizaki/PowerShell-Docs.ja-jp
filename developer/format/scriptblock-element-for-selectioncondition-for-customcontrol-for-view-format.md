---
title: ScriptBlock 要素のビュー (形式) のカスタム コントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7031fa8b-3e2b-4ea8-89cb-95171f467b5a
caps.latest.revision: 6
ms.openlocfilehash: e55d1c5aa533005b258ecbbbf3ed9d55f852eab6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857418"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a>View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。 この要素は、カスタム コントロールのビューを定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素の表示 (カスタム コントロールの CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry EntrySelectedBy SelectionCondition ビュー (形式) のカスタム コントロール用のビュー (形式) スクリプト ブロックの要素のカスタム コントロール用のビュー (形式) SelectionCondition 要素のカスタム コントロール用の形式) CustomItem 要素

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
|[ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|コントロールの定義を使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。 選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
