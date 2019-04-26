---
title: ビュー (形式) のカスタム コントロールの CustomEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066279"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a>View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)

このカスタム エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) EntrySelectedBy CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロール表示 (形式) CustomEntry 要素

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[CustomEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|省略可能な要素です。<br /><br /> この定義を使用するのに必要な条件を定義します。|
|[CustomEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロールのビューの定義を使用して .NET 型のセットを指定します。|
|[EntrySelectedBy CustomEntry (形式) 用の TypeName 要素](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロールのビューの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[表示 (形式) CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|特定の .NET オブジェクトで使用される制御を定義します。|

## <a name="remarks"></a>コメント

少なくとも 1 つの型、選択範囲のセット、またはエントリの選択条件を指定する必要があります。 使用できる子要素の数に上限はありません。

選択条件を使用して、使用するエントリのオブジェクトが特定のプロパティがなどときや、特定のプロパティ値の条件が存在する必要がありますを定義またはスクリプトを評価する`true`します。 選択条件の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。

カスタム コントロールのビューのコンポーネントに関する詳細については、次を参照してください。[カスタムのコントロール ビュー](./creating-custom-controls.md)します。

## <a name="see-also"></a>参照

[CustomEntry (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[CustomEntry (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[EntrySelectedBy CustomEntry (形式) 用の TypeName 要素](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[表示 (形式) CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[カスタム コントロールのビュー](./creating-custom-controls.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
