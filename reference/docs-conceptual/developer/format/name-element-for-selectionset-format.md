---
title: SelectionSet の Name 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362671"
---
# <a name="name-element-for-selectionset-format"></a>SelectionSet の Name 要素 (書式)

選択セットを参照するために使用する名前を指定します。

Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (書式) Selectionsets (形式) の名前要素

## <a name="syntax"></a>構文

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Name` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[SelectionSet 要素 (形式)](./selectionset-element-format.md)|セットの名前で参照できる .NET オブジェクトの1つのセットを定義します。|

## <a name="text-value"></a>テキスト値

選択セットを参照する名前を指定します。 使用できる文字に関する制限はありません。

## <a name="remarks"></a>コメント

ここで指定された名前は、`SelectionSetName` 要素で使用されます。 ビューで使用できる選択セット (ビューには複数の定義を含めることができます)、または選択条件を指定する場合に使用できます。 選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="example"></a>例

この例は、4つの .NET 型を定義する `SelectionSet` 要素を示しています。 選択セットの名前は "FileSystemTypes" です。

```xml
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

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
