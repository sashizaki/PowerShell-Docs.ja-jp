---
title: ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855028"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a>View の CustomControl の EntrySelectedBy の SelectionSetName 要素 (書式)

.NET オブジェクト、リストのエントリのセットを指定します。 エントリに指定できる選択セットの数に制限はありません。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) EntrySelectedBy CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry EntrySelectedBy CustomEntry (形式) 用のビュー (形式) SelectionSetName 要素の要素

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|このカスタム エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

カスタム コントロールの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。

複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。 たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。 選択範囲のセットを定義する詳細については、[選択範囲の設定を定義する](./defining-selection-sets.md)を参照してください。

カスタム コントロールのビューのコンポーネントに関する詳細については、[カスタム コントロールを作成する](./creating-custom-controls.md)を参照してください。

## <a name="see-also"></a>参照

[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[カスタム コントロールのビュー](./creating-custom-controls.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
