---
title: ItemSelectionCondition ListControl (形式) 用のスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064409"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a>ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトを評価するときに`true`条件が満たされ、リスト項目を使用します。 この要素は、リスト ビューを定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries ListEntry の ListControl (形式) のリスト項目要素のListItem ListControl (形式) の ItemSelectionCondition の ListControl (形式) スクリプト ブロックの要素のリスト コントロール (形式) ItemSelectionCondition 要素の ListItems の ListItem 要素を ListControl (形式)

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
|[ItemSelectionCondition ListControl (形式) を ListItem 要素](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|使用するには、このリスト項目の存在する必要がある条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

指定できないかどうかは、この要素が使用される、`PropertyName`要素の選択条件を定義するときにします。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
