---
title: SelectionSet 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861158"
---
# <a name="selectionset-element-format"></a>SelectionSet 要素 (書式)

セットの名前で参照できる .NET オブジェクトのセットを定義します。

構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式)

## <a name="syntax"></a>構文

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSet`要素。 各選択セットには、名前が必要ですし、一連の .NET オブジェクトを指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[SelectionSet (形式) の name 要素](./name-element-for-selectionset-format.md)|必須の要素。<br /><br /> 選択範囲のセットを参照するための名前を指定します。|
|[型の要素 (形式)](./types-element-for-selectionset-format.md)|必須の要素。<br /><br /> 選択範囲で設定された .NET オブジェクトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[SelectionSets 要素の形式](./selectionsets-element-format.md)|書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。|

## <a name="remarks"></a>コメント

継承によって関連付けられているオブジェクトのセットなどの 1 つの名前を使用して参照する関連のオブジェクトのセットがある場合は、選択範囲のセットを使用できます。 ビューを定義するときに、それぞれのビュー内のすべてのオブジェクトを一覧表示するのではなく設定の選択範囲の名前を使用してオブジェクトのセットを指定できます。

一般的な選択範囲のセットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。 このような場合、`SelectionSetName`の子要素、`ViewSelectedBy`と`EntrySelectedBy`要素を使用するデータセットを指定します。 選択範囲のセットの詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。

## <a name="example"></a>例

次の例は、 `SelectionSet` 4 つの .NET 型を定義する要素。

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

[SelectionSet (形式) の name 要素](./name-element-for-selectionset-format.md)

[SelectionSets 要素 (形式)](./selectionsets-element-format.md)

[型の要素 (形式)](./types-element-for-selectionset-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
