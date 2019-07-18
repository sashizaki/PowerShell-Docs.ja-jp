---
title: ファイルの概要を書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe888fee-1fe9-459f-9d62-35732c19a7f8
caps.latest.revision: 13
ms.openlocfilehash: d418cff70c1197aa3c331eed909f49198da139e9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065735"
---
# <a name="formatting-file-overview"></a>書式設定ファイルの概要

コマンド (コマンドレット、関数、およびスクリプト) によって返されるオブジェクトの表示形式は、書式設定ファイル (format.ps1xml ファイル) を使用して定義されます。 などの PowerShell で提供されるコマンドによって返されるこれらのオブジェクトの表示形式を定義する PowerShell によって提供されるこれらのファイルのいくつか、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)によって返されるオブジェクト、`Get-Process`コマンドレット。 ただし、既定の表示形式を上書きする独自のカスタムの書式設定ファイルを作成することもできます。 または、独自のコマンドによって返されるオブジェクトの表示を定義するカスタムの書式設定ファイルを作成することができます。

> [!IMPORTANT]
> 書式設定ファイルは、パイプラインに返されるオブジェクトの要素を特定できません。 パイプラインにオブジェクトが返されると、そのオブジェクトのすべてのメンバーは、いくつかが表示されない場合でも使用です。

PowerShell では、これらの書式設定ファイルでデータを使用して、表示される内容と表示されるデータの書式設定方法を決定します。 表示されるデータには、スクリプトの値またはオブジェクトのプロパティを含めることができます。 スクリプトは、オブジェクトの 2 つのプロパティの値を追加して、データの一部として合計を表示するなどのオブジェクトのプロパティから直接は使用できないいくつかの値を表示する場合に使用されます。 表示されるデータの書式設定は、表示するオブジェクトのビューを定義することで行われます。 オブジェクトごとに 1 つのビューを定義することができます、複数のオブジェクトの 1 つのビューを定義することができます、または同じオブジェクトに対して複数のビューを定義することができます。 定義できるビューの数に制限はありません。

## <a name="common-features-of-formatting-files"></a>書式設定ファイルの一般的な機能

各書式設定ファイルには、ファイルで定義されているすべてのビューで共有できる、次のコンポーネントを定義できます。

- 既定の構成設定、かどうかのテーブルの行に表示されるデータが次の行に表示されます、データが列の幅より長い場合など。 これらの設定の詳細については、次を参照してください。[共通の構成設定を定義する](./defining-common-configuration-features.md)します。

- 書式設定ファイルのビューのいずれかで表示できるオブジェクトを設定します。 これらのセットの詳細については (と呼ばれる*選択セット*) を参照してください[オブジェクト設定を定義する](./defining-selection-sets.md)します。

- 書式設定ファイルのすべてのビューで使用できる一般的なコントロール。 コントロールでは、データの表示方法の詳細な制御を提供します。 コントロールの詳細については、次を参照してください。[カスタム コントロールの定義と](./creating-custom-controls.md)します。

## <a name="formatting-views"></a>書式設定のビュー

書式設定のビューは、テーブル形式、一覧の形式、ワイド形式、およびカスタム形式でオブジェクトを表示できます。 ほとんどの場合、各書式設定の定義は、一連のビューを記述する XML タグで表されます。 それぞれのビューには、ビュー、およびテーブル ビューの列と行情報など、ビューの要素を使用するオブジェクトには、ビューの名前が含まれています。

テーブル ビューまたはスクリプト ブロックの値を 1 つまたは複数の列内のオブジェクトのプロパティを示します。 各列は、オブジェクトまたはスクリプトの値の 1 つのプロパティを表します。 オブジェクト、オブジェクト、またはプロパティとスクリプトの値の組み合わせのプロパティのサブセットのすべてのプロパティを表示するテーブルのビューを定義することができます。 テーブルの各行は、返されたオブジェクトを表します。 テーブル ビューを作成にオブジェクトをパイプするときによく似ています、`Format-Table`コマンドレット。 このビューの詳細については、次を参照してください。[テーブル ビュー](./creating-a-table-view.md)します。

リスト ビュー オブジェクトまたはスクリプトの値が 1 つの列のプロパティを表示します。 リストの各行には、オプションのラベルまたはプロパティ名の後に、プロパティやスクリプトの値が表示されます。 リスト ビューを作成するオブジェクトをパイプするよく似ています、`Format-List`コマンドレット。 このビューの詳細については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。

ワイド ビューには、1 つまたは複数の列でスクリプトの値またはオブジェクトの 1 つのプロパティが一覧表示されます。 ラベルまたはこのビューのヘッダーはありません。 オブジェクトをパイプ処理とよく似ていますワイド ビューの作成、`Format-Wide`コマンドレット。 このビューの詳細については、次を参照してください。[表示幅が広い](./creating-a-wide-view.md)します。

カスタム ビューには、テーブルのビュー、リスト ビュー、またはワイド ビューの厳格な構造に準拠していないオブジェクトのプロパティやスクリプトの値のカスタマイズ可能なビューが表示されます。 スタンドアロンのカスタム ビューを定義する、またはテーブル ビューまたはリスト ビューなどの別のビューで使用されるカスタム ビューを定義することができます。 オブジェクトをパイプ処理とよく似ています、カスタム ビューの作成、`Format-Custom`コマンドレット。 このビューの詳細については、次を参照してください。[カスタム ビュー](./creating-custom-controls.md)します。

## <a name="components-of-a-view"></a>ビューのコンポーネント

次の XML の例では、ビューの基本的な XML コンポーネントを示します。 個々 の XML 要素は、作成するどのビューに応じてを異なりますが、ビューの基本コンポーネントはすべて同じです。

最初に、各ビューでは、`Name`ビューを参照するために使用するユーザー フレンドリ名を指定する要素。 `ViewSelectedBy` 、ビューによって表示される .NET オブジェクトを定義する要素と*コントロール*ビューを定義する要素。

```xml
<ViewDefinitions>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <ListControl>...</ListControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <WideControl>...</WideControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <CustomControl>...</CustomControl>
  </View>
</ViewDefinitions>

```

1 つまたは複数を定義するコントロール要素内で*エントリ*要素。 複数の定義を使用する場合は、.NET オブジェクトを使用して、それぞれの定義を指定する必要があります。 通常、各コントロールの 1 つだけの定義と、1 つのエントリが必要です。

```xml
<ListControl>
  <ListEntries>
    <ListEntry>
      <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
  </ListEntries>
</ListControl>

```

指定したビューの各エントリ要素内で、*項目*.NET プロパティまたはそのビューによって表示されるスクリプトを定義する要素。

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

上記の例に示すように書式設定ファイルが複数のビューを含めることができます、ビューは、複数の定義を含めることができますおよび各定義は複数の項目を含めることができます。

## <a name="example-of-a-table-view"></a>テーブル ビューの例

次の例は、2 つの列を含むテーブルのビューを定義するために使用する XML タグを示しています。 [ViewDefinitions](./viewdefinitions-element-format.md)要素が書式設定ファイルで定義されているすべてのビューのコンテナー要素。 [ビュー](./view-element-format.md)要素は、特定のテーブル、リスト、ビュー、またはカスタム ビューを定義します。 各[ビュー](./view-element-format.md)要素、[名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します、 [ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビュー、およびさまざまなを使用するオブジェクトを定義します。コントロールの要素 (など、`TableControl`要素の次の例に示すように)、ビューの種類を定義します。

```xml
<ViewDefinitions>
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[テーブル ビューを作成します。](./creating-a-table-view.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[カスタム コントロールの作成](./creating-custom-controls.md)

[PowerShell の書式設定およびファイルの種類の作成](./writing-a-powershell-formatting-file.md)
