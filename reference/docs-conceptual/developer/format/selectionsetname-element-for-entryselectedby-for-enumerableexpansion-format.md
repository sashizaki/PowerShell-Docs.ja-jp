---
title: 列挙 Able膨張 (Format) の EntrySelectedBy の SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368331"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)

この定義によって展開される .NET 型のセットを指定します。

Configuration 要素 (Format) DefaultSettings 要素 (format) には、EntrySelectedBy 要素 (format) の entryselectedby 要素 (format) を指定します。この場合、EntrySelectedBy の SelectionSetName 要素を指定します。列挙 Able展開 (形式)

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開 (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)|この定義によって展開される .NET コレクションオブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

各定義には、1つ以上の型名、選択セット、または選択条件を指定する必要があります。

選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。 たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。 選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="see-also"></a>参照

[選択セットの定義](./defining-selection-sets.md)

[列挙 Able展開 (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
