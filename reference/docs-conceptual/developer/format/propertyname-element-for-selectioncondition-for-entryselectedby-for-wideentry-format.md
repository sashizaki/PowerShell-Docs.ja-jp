---
title: WideEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340abb12-6df1-42f4-bdae-b0509c90952c
caps.latest.revision: 11
ms.openlocfilehash: 196877b97db9ed0592e357486c1318dc1e7efd31
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362241"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a>WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、定義が使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionCondition 要素の (Format) 項目の EntrySelectedBy 要素Entryselectedby for WideEntry (Format) PropertyName Element for EntrySelectedBy for WideEntry (Format)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|この定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET プロパティ名を指定します。

## <a name="remarks"></a>コメント

選択条件では、少なくとも1つのプロパティ名または評価対象のスクリプトを指定する必要がありますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。

## <a name="see-also"></a>参照

[ワイドビューの作成](./creating-a-wide-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[WideEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
