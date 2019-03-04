---
title: コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859538"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a>View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)

このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry ビュー (形式) のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロール

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。 少なくとも 1 つの型、選択範囲のセット、または定義の選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> この定義を使用するのに必要な条件を定義します。|
|[コントロールが表示されます (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロールの定義を使用して .NET 型のセットを指定します。|
|[コントロールが表示されます (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロールの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

選択条件を使用して、使用する定義のオブジェクトに特定のプロパティがある場合などときや、特定のプロパティ値の条件が存在する必要がありますを定義またはスクリプトを評価する`true`します。 選択条件の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
