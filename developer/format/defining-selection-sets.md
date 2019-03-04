---
title: 選択範囲のセットを定義する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858928"
---
# <a name="defining-selection-sets"></a>選択セットを定義する

複数のビューとコントロールを作成する場合は、選択範囲のセットとして参照されるオブジェクトのセットを定義できます。 選択範囲のセットでは、各ビューまたはコントロールの繰り返しに定義することがなく 1 回、オブジェクトを定義することができます。 通常、選択範囲のセットは、関連する .NET オブジェクトのセットがある場合に使用されます。 たとえば、`FileSystem`書式設定ファイル (FileSystem.format.ps1xml) がいくつかのビューを使用して、ファイル システムの種類の選択範囲のセットを定義します。

## <a name="where-selection-sets-are-defined-and-referenced"></a>選択範囲のセットが定義および参照を

すべてのビューと書式設定ファイルで定義されているコントロールで使用できる一般的なデータの一部としては、選択範囲のセットを定義します。 次の例では、次の 3 つの選択範囲のセットを定義する方法を示します。

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

選択範囲を参照する次のように設定します。

- 各ビューでは、`ViewSelectedBy`ビューを使用して表示されるオブジェクトを定義する要素。 `ViewSelectedBy`要素には、`SelectionSetName`選択範囲を指定する子要素がビューの使用のすべての定義を設定します。 ビューから参照できるように選択セットの数に制限はありません。

- ビューまたはコントロールの各定義における、`EntrySelectedBy`要素は、その定義を使用して表示されるオブジェクトを定義します。 通常、ビューまたはコントロールに 1 つだけ定義して、オブジェクトが定義されているため、`ViewSelectedBy`要素。 `EntrySelectedBy`定義の要素には、`SelectionSetName`選択範囲のセットを指定する子要素。 選択の定義のセットを指定する場合の他の子要素のいずれかを指定できません、`EntrySelectedBy`要素。

- ビューまたはコントロールの各定義における、`SelectionCondition`定義を使用する場合の条件を指定する要素を使用できます。 `SelectionCondition`要素には、`SelectionSetName`選択範囲のセットを示す子要素が条件をトリガーします。 選択範囲のセットで定義されたオブジェクトのいずれかが表示される場合は、条件がトリガーされます。 これらの条件を設定する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="selection-set-example"></a>選択範囲のセットの例

次の例では、選択セットから直接実行する、 `FileSystem` Windows PowerShell によって提供されるファイルの書式設定します。 その他の Windows PowerShell の書式設定ファイルの詳細については、次を参照してください。 [Windows PowerShell の書式設定ファイル](./powershell-formatting-files.md)します。

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

前の選択範囲のセットが参照されている、`ViewSelectedBy`テーブル ビューの要素。

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a>XML 要素

 定義できる選択セットの数に制限はありません。 次の XML 要素を使用して、選択範囲のセットを作成できます。

- [SelectionSets](./selectionsets-element-format.md)ビューによって参照されている .NET オブジェクトのセットと書式設定ファイルのコントロール要素を定義します。

- [SelectionSet](./selectionset-element-format.md)要素は、.NET オブジェクトの 1 つのセットを定義します。

- [名前](./name-element-for-selectionset-format.md)要素は、選択範囲のセットを参照するために使用される名前を指定します。

- [型](./types-element-for-selectionset-format.md)要素は、選択範囲のセットのオブジェクトの .NET 型を指定します。 (ファイルの書式設定、内でオブジェクトが指定されてをその .NET 型です。)

 次の XML 要素を使用して、選択範囲のセットを指定します。

- 次の要素は、ビューのすべての定義で使用する設定の選択範囲を指定します。

    - [ViewSelectedBy (形式) の SelectionSetName 要素](./selectionsetname-element-for-viewselectedby-format.md)

    - [GroupBy (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- 次の要素は、1 つのビュー定義で使用される選択セットを指定します。

    - [ListControl (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [TableControl (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [WideControl (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- 次の要素が共通で使用される選択範囲のセットを指定し、コントロールの定義を表示します。

    - [コントロールが表示されます (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- 次の要素を展開するには、どのオブジェクトを定義するときに使用される選択セットを指定します。

    - [EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- 次の要素は、選択条件で使用される選択範囲のセットを指定します。

    - [構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [ビュー (形式) のカスタム コントロールの SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [EntrySelectedBy ListEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [TableControl (形式) の EntrySelectedBy の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [GroupBy (形式) の SelectionCondition SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a>参照

[SelectionSets](./selectionsets-element-format.md)

[SelectionSet](./selectionset-element-format.md)

[名前](./name-element-for-selectionset-format.md)

[型](./types-element-for-selectionset-format.md)

[PowerShell の書式設定ファイル](./powershell-formatting-files.md)

[データが表示される場合の条件の定義](./defining-conditions-for-displaying-data.md)

[PowerShell の書式設定およびファイルの種類の作成](./writing-a-powershell-formatting-file.md)
