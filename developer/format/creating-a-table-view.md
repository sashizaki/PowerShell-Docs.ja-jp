---
title: テーブル ビューを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f405afb-70b5-4fe0-9986-bc07401d93fd
caps.latest.revision: 23
ms.openlocfilehash: 862f942facafff6cea66c4f8f1040772c6a62ec3
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057367"
---
# <a name="creating-a-table-view"></a>テーブル ビューを作成する

テーブル ビューでは、1 つまたは複数の列のデータを表示します。 テーブル内の各行は、.NET オブジェクトを表し、テーブルの各列は、オブジェクトまたはスクリプトの値のプロパティを表します。 オブジェクトのすべてのプロパティまたはオブジェクトのプロパティのサブセットを表示するテーブルのビューを定義することができます。

## <a name="a-table-view-display"></a>テーブル ビューの表示

次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトによって返される、 [Get-service](/powershell/module/microsoft.powershell.management/get-service)コマンドレット。 Windows PowerShell には、このオブジェクトのテーブルに表示するビューが定義されて、`Status`プロパティ、`Name`プロパティ (このプロパティは、エイリアス プロパティを`ServiceName`プロパティ)、および`DisplayName`プロパティ。 テーブル内の各行は、コマンドレットによって返されるオブジェクトを表します。

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a>テーブル ビューを定義します。

次の XML は、テーブル ビューのスキーマを表示するため、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。 テーブル ビューで表示する各プロパティを指定する必要があります。

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>8</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>18</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>38</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

次の XML 要素は、リスト ビューの定義に使用されます。

- [ビュー](./view-element-format.md)要素は、テーブル ビューの親要素です。 (これは、一覧、幅をカスタム コントロールの表示については、同じ親要素です)。

- [名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します。 この要素は、すべてのビューに必要です。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。 この要素が必要です。

- [GroupBy](./groupby-element-for-view-format.md)オブジェクトの新しいグループが表示される場合 (この例では説明しません) 要素を定義します。 特定のプロパティまたはスクリプトの値が変更されるたびに新しいグループが開始されます。 この要素は省略可能です。

- [コントロール](./controls-element-for-view-format.md)要素 (この例では表示されません)、テーブル ビューで定義されているカスタム コントロールを定義します。 コントロールでは、さらに、データの表示方法を指定する方法を提供します。 この要素は省略可能です。 ビューがその独自のカスタム コントロールを定義できます。 または書式設定ファイルに任意のビューで使用できる一般的なコントロールを使用できます。 カスタム コントロールの詳細については、[カスタム コントロールを作成する](./creating-custom-controls.md)を参照してください。

- [HideTableHeaders](./hidetableheaders-element-format.md)要素 (この例では表示されません) では、テーブルでは、テーブルの上部にある任意のラベルは表示されませんを指定します。 この要素は省略可能です。

- [TableControl](./tablecontrol-element-format.md)テーブルのヘッダーと行情報を定義する要素。 その他のすべてのビューと同様に、テーブル ビューを表示できますオブジェクトのプロパティの値またはスクリプトによって生成される値。

## <a name="defining-column-headers"></a>列ヘッダーを定義します。

1. [TableHeaders](./tableheaders-element-format.md)要素とその子要素は、テーブルの上部に表示される内容を定義します。

2. [TableColumnHeader](./tablecolumnheader-element-format.md)要素は、テーブルの列の上部に表示される内容を定義します。 ヘッダーを表示する順序でこれらの要素を指定します。

   数は、次のように使用できる、これらの要素の数に制限はありません[TableColumnHeader](./tablecolumnheader-element-format.md)テーブル ビュー内の要素の数に一致する必要があります[TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)を使用する要素。

3. [ラベル](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)要素が表示されるテキストを指定します。 この要素は省略可能です。

4. [幅](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)要素 (文字) で、列の幅を指定します。 この要素は省略可能です。

5. [配置](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、ラベルを表示する方法を指定します。 ラベルの右側に、左側に配置または中央に配置できます。 この要素は省略可能です。

## <a name="defining-the-table-rows"></a>テーブルの行を定義します。

テーブル ビューでの子要素を使用して、どのようなデータをテーブルの行に表示を指定する 1 つまたは複数の定義を提供できます、 [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)要素。 テーブルの行に対して複数の定義を指定できますが、行のヘッダーはどのような行定義の使用に関係なく、同じことに注意してください。 通常、テーブルには、1 つだけ定義があります。

ビューでのいくつかのプロパティの値を表示する 1 つの定義は、次の例では、 [System.Diagnostics.Process でしょうか。Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process)オブジェクト。 テーブル ビューでは、その行のプロパティの値またはスクリプト (この例では表示されません) の値を表示できます。

```xml
<TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>

```

行の定義を提供する、次の XML 要素を使用できます。

- [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)要素とその子要素は、テーブルの行に表示される内容を定義します。

- [TableRowEntry](./listentry-element-for-listcontrol-format.md)要素は、行の定義を提供します。 少なくとも 1 つ[TableRowEntry](./listentry-element-for-listcontrol-format.md)が必要です。 ただし、追加できる要素の数に上限はありません。 ほとんどの場合、ビューは 1 つだけ定義になります。

- [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。 この要素は省略可能と複数を定義する場合にのみ必要です[TableRowEntry](./listentry-element-for-listcontrol-format.md)さまざまなオブジェクトを表示する要素。

- [ラップ](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)要素は、次の行を列の幅を超えるテキストが表示されることを指定します。 既定では、列幅を超えるテキストは切り捨てられます。

- [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)プロパティまたはスクリプトの行の表示が値を持つ要素を定義します。

- [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)プロパティまたは値を持つが、行の列に表示されているスクリプト要素を定義します。 A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、行の各列は必須です。 最初のエントリには、最初の列、列と 2 番目の上から 2 番目のエントリが表示されます。

- [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示プロパティを指定します。 プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。

- [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示するスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

- [FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。 この要素は省略可能です。

- [配置](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、プロパティ、またはスクリプトの値を表示する方法を指定します。 値の右側に、左側に配置または中央に配置できます。 この要素は省略可能です。

## <a name="defining-the-objects-that-use-the-table-view"></a>テーブル ビューを使用するオブジェクトを定義します。

.NET オブジェクトを使用して、テーブル ビューを定義する 2 つの方法はあります。 使用することができます、 [ViewSelectedBy](./viewselectedby-element-format.md)するか、ビューのすべての定義を表示できるオブジェクトを定義する要素を使用できる、 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)によって表示されるオブジェクトを定義する要素、ビューの定義を特定します。 ほとんどの場合、ビューでは 1 つだけ定義は、オブジェクトは通常で定義されるため、 [ViewSelectedBy](./viewselectedby-element-format.md)要素。

次の例は、テーブルのビューを使用して表示されるオブジェクトを定義する方法を示します、 [ViewSelectedBy](./viewselectedby-element-format.md)と[TypeName](./typename-element-for-viewselectedby-format.md)要素。 数に制限はありません[TypeName](./typename-element-for-viewselectedby-format.md)要素を指定できますが、およびその順序は重要ではありません。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

次の XML 要素を使用して、テーブル ビューで使用されるオブジェクトを指定することができます。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。

- [TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .NET オブジェクトを指定します。 完全修飾 .NET 型名が必要です。 少なくとも 1 つの型またはビューの設定の選択範囲を指定する必要がありますが、指定できる要素の最大数はありません。

次の例では、 [ViewSelectedBy](./viewselectedby-element-format.md)と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素。 関連する一連の同じオブジェクトのリスト ビューを定義する場合など、複数のビューおよびテーブル ビューを使用して表示されるオブジェクトがある選択範囲のセットを使用します。 選択範囲のセットを作成する方法の詳細については、[選択範囲のセットを定義する](./defining-selection-sets.md)を参照してください。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

次の XML 要素を使用して、リスト ビューで使用されるオブジェクトを指定することができます。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、一連のビューで表示できるオブジェクトを指定します。 少なくとも 1 つの選択範囲のセットまたはビューの種類を指定する必要がありますが、指定できる要素の最大数はありません。

次の例は、ビューを使用してテーブルの特定の定義で表示されるオブジェクトを定義する方法を示します、 [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素。 この要素を使用して、オブジェクト、オブジェクトの選択範囲のセットまたは定義を使用する場合を指定する選択条件の .NET 型名を指定できます。 選択条件を作成する方法の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。

> [!NOTE]
> テーブル ビューの複数の定義を作成するときに、別の列ヘッダーを指定することはできません。 どのようなオブジェクトが表示されるなど、テーブルの行に表示される内容のみを指定できます。

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

リスト ビューの特定の定義で使用されるオブジェクトを指定する、次の XML 要素を使用できます。

- [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素定義によって表示されるオブジェクトを定義します。

- [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)要素を定義して表示されている .NET オブジェクトを指定します。 この要素を使用する場合は、完全修飾 .NET 型名が必要です。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。

- [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義で表示できるオブジェクトのセットを指定します。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。

- [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義を使用するのに必要な条件を指定します。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。 選択条件を定義する詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。

## <a name="using-format-strings"></a>書式指定文字列を使用します。

さらに、データの表示方法を定義するビューには、書式設定文字列を追加できます。 次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

次の XML 要素を使用して、書式パターンを指定することができます。

- [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)プロパティまたは値を持つが、行の列に表示されているスクリプト要素を定義します。 A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、行の各列は必須です。 最初のエントリには、最初の列、列と 2 番目の上から 2 番目のエントリが表示されます。

- [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示プロパティを指定します。 プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。

- [FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。

次の例では、`ToString`スクリプトの値の書式設定メソッドが呼び出されます。 スクリプトでは、オブジェクトのすべてのメソッドを呼び出すことができます。 そのため、オブジェクトが、メソッドがなど`ToString`、書式設定パラメーターを持つ、スクリプトは、スクリプトの出力値の書式を指定するには、そのメソッドを呼び出すことができます。

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

次の XML 要素を呼び出すことができます、`ToString`メソッド。

- [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)プロパティまたは値を持つが、行の列に表示されているスクリプト要素を定義します。 A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、行の各列は必須です。 最初のエントリには、最初の列、列と 2 番目の上から 2 番目のエントリが表示されます。

- [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示するスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
