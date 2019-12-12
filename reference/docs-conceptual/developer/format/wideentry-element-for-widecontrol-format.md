---
title: WideControl の WideEntry 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367901"
---
# <a name="wideentry-element-for-widecontrol-format"></a>WideControl の WideEntry 要素 (書式)

ワイドビューの定義を提供します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (Format)

## <a name="syntax"></a>構文

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`WideEntry` 要素の属性、子要素、および親要素について説明します。 1つの `WideItem` 子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[WideEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-wideentry-format.md)|省略可能な要素です。<br /><br /> このワイドエントリ定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|
|[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)|必須の要素です。<br /><br /> 値が表示されるプロパティまたはスクリプトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[WideEntries 要素 (Format)](./wideentries-element-for-widecontrol-format.md)|ワイドビューの定義を提供します。|

## <a name="remarks"></a>コメント

ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。 他の種類のビューとは異なり、各ビュー定義に指定できる項目要素は1つだけです。 ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

次の例は、単一の `WideItem` 要素を定義する `WideEntry` 要素を示しています。 `WideItem` 要素は、ビューに値が表示されるプロパティを定義します。

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。

## <a name="see-also"></a>参照

[ワイドビューの作成](./creating-a-wide-view.md)

[WideEntry の SelectionCondition 要素 (形式)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry の SelectionSetName 要素 (形式)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry の TypeName 要素 (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[WideEntries 要素 (Format)](./wideentries-element-for-widecontrol-format.md)

[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
