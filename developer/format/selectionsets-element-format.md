---
title: SelectionSets 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebbac73a-1c99-4388-9f47-703cd024dc6d
caps.latest.revision: 18
ms.openlocfilehash: a9356635d60d5f8c5d4dec4ec8b7d0aea2b037dd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853568"
---
# <a name="selectionsets-element-format"></a>SelectionSets 要素 (書式)

書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。 ビューおよび書式設定ファイルのコントロールは、選択範囲のセットの名前のみを使用してオブジェクトの完全なセットを参照できます。

構成要素 SelectionSets 要素の形式

## <a name="syntax"></a>構文

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSets`要素。 各子要素は、セットの名前で参照できるオブジェクトのセットを定義します。 子要素の順序は大きくありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[SelectionSet 要素 (形式)](./selectionset-element-format.md)|必須の要素。<br /><br /> セットの名前で参照できる .NET オブジェクトの 1 つのセットを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成要素](./configuration-element-format.md)|書式設定ファイルの最上位の要素を表します。|

## <a name="remarks"></a>コメント

継承によって関連付けられているオブジェクトのセットなどの 1 つの名前を使用して参照する関連のオブジェクトのセットがある場合は、選択範囲のセットを使用できます。 ビューを定義するときに、それぞれのビュー内のすべてのオブジェクトを一覧表示するのではなく設定の選択範囲の名前を使用してオブジェクトのセットを指定できます。

一般的な選択範囲のセットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。 このような場合、`SelectionSetName`の子要素、`ViewSelectedBy`と`EntrySelectedBy`要素を使用するデータセットを指定します。 選択範囲のセットの詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。

## <a name="see-also"></a>参照

[構成要素](./configuration-element-format.md)

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[SelectionSet 要素 (形式)](./selectionset-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
