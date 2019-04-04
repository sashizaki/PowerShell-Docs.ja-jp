---
title: SelectionSet (形式) の要素の種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862378"
---
# <a name="types-element-for-selectionset-format"></a>SelectionSet の Types 要素 (書式)

選択範囲で設定された .NET オブジェクトを定義します。

構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式) 型の要素 (形式)

## <a name="syntax"></a>構文

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Types`要素。 少なくとも 1 つの子要素がありますが、追加できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[TypeName 要素の種類 (形式)](./typename-element-for-types-format.md)|必須の要素。<br /><br /> 選択範囲のセットに属する .NET オブジェクトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[SelectionSet 要素 (形式)](./selectionset-element-format.md)|セットの名前で参照できる .NET オブジェクトのセットを定義します。|

## <a name="remarks"></a>コメント

この要素で定義されているオブジェクトがビューの定義によって、ビューで使用できる選択セットを構成する (ビューが複数の定義を持つ) は、選択条件を指定する場合またはします。  選択範囲のセットの詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。

## <a name="example"></a>例

この例では、 `SelectionSet` 4 つの .NET 型を定義する要素。

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

[オブジェクトのセットを定義します。](./defining-selection-sets.md)

[SelectionSet 要素 (形式)](./selectionset-element-format.md)

[TypeName 要素の種類 (形式)](./typename-element-for-types-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
