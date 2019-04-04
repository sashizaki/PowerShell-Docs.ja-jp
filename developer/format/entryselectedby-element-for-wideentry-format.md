---
title: WideEntry (形式) の要素を EntrySelectedBy |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854978"
---
# <a name="entryselectedby-element-for-wideentry-format"></a>WideEntry の EntrySelectedBy 要素 (書式)

この定義の表示幅が広いまたは条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素を WideEntry (形式)

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> 使用するには、この表示幅が広い定義を満たす必要がある条件を定義します。|
|[WideEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> この表示幅が広い定義を使用する .NET 型のセットを指定します。|
|[EntrySelectedBy WideEntry (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-wideentry-format.md)|省略可能な要素です。<br /><br /> この表示幅が広い定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideEntry 要素 (形式)](./wideentry-element-for-widecontrol-format.md)|ワイド ビューの定義を提供します。|

## <a name="remarks"></a>コメント

少なくとも 1 つの型、選択範囲のセット、または表示幅が広い定義の選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件を使用して、定義オブジェクトに特定のプロパティがある場合など、使用するのに必要な条件を定義または特定のプロパティの値またはスクリプトの値を評価する`true`します。 選択条件の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。

ワイド ビューの他のコンポーネントに関する詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。

## <a name="see-also"></a>参照

[WideEntry 要素 (形式)](./wideentry-element-for-widecontrol-format.md)

[WideEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[EntrySelectedBy WideEntry (形式) 用の TypeName 要素](./typename-element-for-entryselectedby-for-wideentry-format.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[データを表示するための条件を定義します。](./defining-conditions-for-displaying-data.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
