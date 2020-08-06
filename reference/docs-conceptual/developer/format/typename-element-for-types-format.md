---
title: 型の TypeName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 40fad73c66124d6c3b0d969b4268713a492c963a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772537"
---
# <a name="typename-element-for-types-format"></a>Types の TypeName 要素 (書式)

選択セットに属するオブジェクトの .NET 型を指定します。

Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (format) Types 要素 (format) 型の TypeName 要素 (Format)

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。 `TypeName`選択セットには、少なくとも1つの要素を含める必要があります。

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

## <a name="remarks"></a>解説

継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。 ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。

共通選択セットは、書式設定ファイルのビューを定義するときに、名前によって指定されます。 このような場合は、 `SelectionSetName` ビューの要素の子要素によって `ViewSelectedBy` セットが指定されます。 ただし、ビューのエントリごとに、そのビューのエントリのみに適用される選択セットを指定することもできます。 選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="example"></a>例

次の例は、 `SelectionSet` 4 つの .net 型を定義する要素を示しています。

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

[選択セットを定義する](./defining-selection-sets.md)

[SelectionSet 要素 (書式)](./selectionset-element-format.md)

[SelectionSets 要素 (書式)](./selectionsets-element-format.md)

[Types 要素 (Format)](./types-element-for-selectionset-format.md)

[Windows PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
