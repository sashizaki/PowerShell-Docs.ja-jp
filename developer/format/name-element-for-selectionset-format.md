---
title: SelectionSet (形式) の要素の名前を付けます |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858168"
---
# <a name="name-element-for-selectionset-format"></a>SelectionSet の Name 要素 (書式)

選択範囲のセットを参照するための名前を指定します。

SelectionSet (形式) の構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式) の名前要素

## <a name="syntax"></a>構文

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Name`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[SelectionSet 要素 (形式)](./selectionset-element-format.md)|セットの名前で参照できる .NET オブジェクトの 1 つのセットを定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットを参照する名前を指定します。 どのような文字に関する制限は使用できません。

## <a name="remarks"></a>コメント

ここで指定した名前で使用されます、`SelectionSetName`要素。 ビューの定義によって、ビューで使用できる選択セット (ビューが複数の定義を持つ) は、選択条件を指定する場合またはします。 選択範囲のセットの詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。

## <a name="example"></a>例

この例では、 `SelectionSet` 4 つの .NET 型を定義する要素。 選択範囲のセットの名前は、"FileSystemTypes"です。

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

## <a name="see-also"></a>参照

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[SelectionSet 要素 (形式)](./selectionset-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
