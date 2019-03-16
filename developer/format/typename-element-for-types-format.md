---
title: TypeName 要素の種類 (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057928"
---
# <a name="typename-element-for-types-format"></a>Types の TypeName 要素 (書式)

選択範囲のセットに属しているオブジェクトの .NET 型を指定します。

構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式) の種類 (形式) の要素 (形式) の TypeName 要素の型します。

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。 少なくとも 1 つ`TypeName`選択セットに要素を含める必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[型の要素 (形式)](./types-element-for-selectionset-format.md)|選択範囲で設定された .NET オブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

継承によって関連付けられているオブジェクトのセットなどの 1 つの名前を使用して参照する関連のオブジェクトのセットがある場合は、選択範囲のセットを使用できます。 ビューを定義するときに、それぞれのビュー内のすべてのオブジェクトを一覧表示するのではなく設定の選択範囲の名前を使用してオブジェクトのセットを指定できます。

一般的な選択範囲のセットは、書式設定ファイルのビューを定義するときに、名前によって指定されます。 このような場合、`SelectionSetName`の子要素、`ViewSelectedBy`ビューの要素がセットを指定します。 ただし、ビューのさまざまなエントリは、ビューのエントリのみに適用される選択セットも指定できます。 選択範囲のセットの詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。

## <a name="example"></a>例

次の例は、 `SelectionSet` 4 つの .NET 型を定義する要素。

```
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a>参照

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[SelectionSet 要素 (形式)](./selectionset-element-format.md)

[SelectionSets 要素 (形式)](./selectionsets-element-format.md)

[型の要素 (形式)](./types-element-for-selectionset-format.md)

[Windows PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
