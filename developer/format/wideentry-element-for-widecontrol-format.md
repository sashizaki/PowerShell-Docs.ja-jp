---
title: WideControl (形式) の要素を WideEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856528"
---
# <a name="wideentry-element-for-widecontrol-format"></a>WideControl の WideEntry 要素 (書式)

ワイド ビューの定義を提供します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式)

## <a name="syntax"></a>構文

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`WideEntry`要素。 1 つを指定する必要があります`WideItem`子要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[WideEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-wideentry-format.md)|省略可能な要素です。<br /><br /> このエントリのワイド定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。|
|[WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)|必須の要素。<br /><br /> プロパティまたは値が表示されているスクリプトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideEntries 要素 (形式)](./wideentries-element-for-widecontrol-format.md)|表示幅が広いの定義を提供します。|

## <a name="remarks"></a>コメント

ワイド ビューは、1 つのプロパティの値または各オブジェクトのスクリプト値を表示する一覧の形式です。 その他の種類のビューとは異なり、各ビューの定義の項目要素を 1 つだけを指定できます。 ワイド ビューの他のコンポーネントの詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。

## <a name="example"></a>例

次の例は、 `WideEntry` 、1 つを定義する要素`WideItem`要素。 `WideItem`要素値を持つが、ビューに表示プロパティを定義します。

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

## <a name="see-also"></a>参照

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[WideEntry (形式) の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (形式) の SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry (形式) の TypeName 要素](./typename-element-for-entryselectedby-for-wideentry-format.md)

[WideEntries 要素 (形式)](./wideentries-element-for-widecontrol-format.md)

[WideItem 要素 (形式)](./wideitem-element-for-widecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
