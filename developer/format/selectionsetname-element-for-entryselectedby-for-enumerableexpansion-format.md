---
title: EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862748"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)

この定義で展開される .NET 型のセットを指定します。

構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EntrySelectedBy の EnumerableExpansion (形式) SelectionSetName 要素EnumerableExpansion (形式)

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
|[EnumerableExpansion (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)|この定義で展開される .NET コレクション オブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

各定義には、1 つまたは複数の型名、選択範囲のセット、または選択条件を指定する必要があります。

複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。 たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。 選択範囲のセットを定義する詳細については、次を参照してください。[を定義する設定のビューのオブジェクトを](./defining-selection-sets.md)します。

## <a name="see-also"></a>参照

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[EnumerableExpansion (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
