---
title: 型の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368031"
---
# <a name="typename-element-for-types-format"></a>Types の TypeName 要素 (書式)

選択セットに属するオブジェクトの .NET 型を指定します。

Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (format) Types 要素 (format) 型の TypeName 要素 (Format)

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。 選択セットには、少なくとも1つの `TypeName` 要素が含まれている必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Types 要素 (Format)](./types-element-for-selectionset-format.md)|選択セット内の .NET オブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。 ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。

共通選択セットは、書式設定ファイルのビューを定義するときに、名前によって指定されます。 このような場合、ビューの `ViewSelectedBy` 要素の `SelectionSetName` 子要素によって、セットが指定されます。 ただし、ビューのエントリごとに、そのビューのエントリのみに適用される選択セットを指定することもできます。 選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="example"></a>例

次の例は、4つの .NET 型を定義する `SelectionSet` 要素を示しています。

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

## <a name="see-also"></a>関連項目

[選択セットの定義](./defining-selection-sets.md)

[SelectionSet 要素 (形式)](./selectionset-element-format.md)

[SelectionSets 要素 (Format)](./selectionsets-element-format.md)

[Types 要素 (Format)](./types-element-for-selectionset-format.md)

[Windows PowerShell のフォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
