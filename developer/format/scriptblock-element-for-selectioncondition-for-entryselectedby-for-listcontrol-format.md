---
title: SelectionCondition EntrySelectedBy ListControl (形式) のためのスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057775"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、一覧のエントリを使用します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy ListEntry (形式) のためのスクリプト ブロック要素を ListEntry (形式)

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
|[ListEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|このリストのエントリを使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。 (選択条件を使用する方法の詳細については、次を参照してください[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)。)。

リスト ビューの他のコンポーネントの詳細については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。

## <a name="see-also"></a>参照

[ListEntry 要素 (形式)](./listentry-element-for-listcontrol-format.md)

[SelectionCondition EntrySelectedBy ListEntry (形式) のための PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[ListEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[リスト ビュー](./creating-a-list-view.md)

[ビューのエントリまたは項目を使用する場合の条件の定義](./defining-conditions-for-displaying-data.md)

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
