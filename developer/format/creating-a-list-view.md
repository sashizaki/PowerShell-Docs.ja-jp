---
title: リスト ビューの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c7a40ca-1786-46f0-bab5-6ce229daa7ee
caps.latest.revision: 14
ms.openlocfilehash: 25d24063501196d44e0f806a55bb699c82f771ce
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861578"
---
# <a name="creating-a-list-view"></a>リスト ビューを作成する

リスト ビューでは、(順番に) に 1 つの列のデータを表示します。 一覧に表示されるデータには、.NET プロパティの値またはスクリプトの値を指定できます。

## <a name="a-list-view-display"></a>リスト ビューの表示

次の出力は、Windows PowerShell でのプロパティを表示する方法を示しています。 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトによって返される、 [Get-service](/powershell/module/microsoft.powershell.management/get-service)コマンドレット。 この例では、前のオブジェクトからの空白行で区切られた各オブジェクトに、3 つのオブジェクトは返されました。

```powershell
Get-Service | format-list
```

```output
Name                : AEADIFilters
DisplayName         : Andrea ADI Filters Service
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess

Name                : AeLookupSvc
DisplayName         : Application Experience
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32ShareProcess

Name                : AgereModemAudio
DisplayName         : Agere Modem Call Progress Audio
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess
...
```

## <a name="defining-the-list-view"></a>リスト ビューを定義します。

次の XML は、リスト ビューのスキーマのいくつかのプロパティを表示するため、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。 リスト ビューで表示する各プロパティを指定する必要があります。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

次の XML 要素は、リスト ビューの定義に使用されます。

- [ビュー](./view-element-format.md)要素はリスト ビューの親要素です。 (これは、テーブル、ビューの幅をカスタム コントロールの同じ親要素です)。

- [名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します。 この要素は、すべてのビューに必要です。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。 この要素が必要です。

- [GroupBy](./groupby-element-for-view-format.md)オブジェクトの新しいグループが表示される要素を定義します。 特定のプロパティまたはスクリプトの値が変更されるたびに新しいグループが開始されます。 この要素は省略可能です。

- [コントロール](./controls-element-for-view-format.md)要素がリスト ビューで定義されているカスタム コントロールを定義します。 コントロールでは、さらに、データの表示方法を指定する方法を提供します。 この要素は省略可能です。 ビューがその独自のカスタム コントロールを定義できます。 または書式設定ファイルに任意のビューで使用できる一般的なコントロールを使用できます。 カスタム コントロールの詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。

- [ListControl](./listcontrol-element-format.md)要素は、ビューに表示される内容と書式設定方法を定義します。 その他のすべてのビューと同様に、リスト ビューを表示できますオブジェクトのプロパティの値またはスクリプトによって生成された値。

単純なリスト ビューを定義する完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (Basic)](./list-view-basic.md)します。

## <a name="providing-definitions-for-your-list-view"></a>リスト ビューの定義を提供します。

リスト ビューには、子要素を使用して 1 つまたは複数の定義ができるように、 [ListControl](./listcontrol-element-format.md)要素。 通常、ビューには、1 つだけ定義があります。 ビューでのいくつかのプロパティを表示する 1 つの定義は、次の例では、 [System.Diagnostics.Process でしょうか。Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process)オブジェクト。 リスト ビューには、プロパティの値またはスクリプト (この例では表示されません) の値を表示できます。

```xml
<ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>

```

リスト ビューの定義を提供する、次の XML 要素を使用できます。

- [ListControl](./listcontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。

- [ListEntries](./listentries-element-for-listcontrol-format.md)要素は、ビューの定義を提供します。 ほとんどの場合、ビューは 1 つだけ定義になります。 この要素が必要です。

- [ListEntry](./listentry-element-for-listcontrol-format.md)要素は、ビューの定義を提供します。 少なくとも 1 つ[ListEntry](./listentry-element-for-listcontrol-format.md)が必要です。 ただし、追加できる要素の数に上限はありません。 ほとんどの場合、ビューは 1 つだけ定義になります。

- [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。 この要素は省略可能と複数を定義する場合にのみ必要です[ListEntry](./listentry-element-for-listcontrol-format.md)さまざまなオブジェクトを表示する要素。

- [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md)要素は、プロパティと値を持つがリスト ビューの行に表示されるスクリプトを指定します。

- [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md)要素は、プロパティまたはリスト ビューの行の値が表示されているスクリプトを指定します。 リスト ビューには、少なくとも 1 つのプロパティまたはスクリプトを指定する必要があります。 指定できる行の数に上限はありません。

- [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素の値が行に表示プロパティを指定します。 プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。

- [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素の値が行に表示するスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

- [ラベル](./label-element-for-listitem-for-listcontrol-format.md)要素は、行のプロパティまたはスクリプトの値の左側に表示されるラベルを指定します。 この要素は省略可能です。 ラベルが指定されていない場合、プロパティまたはスクリプトの名前が表示されます。 完全な例を参照してください。[リスト ビュー (ラベル)](./list-view-labels.md)します。

- [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)要素は、行を表示するのに必要な条件を指定します。 リスト ビューに条件を追加する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。 この要素は省略可能です。

- [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md)要素は、プロパティ、またはスクリプトの値を表示するために使用するパターンを指定します。 この要素は省略可能です。

単純なリスト ビューを定義する完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (Basic)](./list-view-basic.md)します。

## <a name="defining-the-objects-that-use-the-list-view"></a>リスト ビューを使用するオブジェクトを定義します。

.NET オブジェクトを使用して、リスト ビューを定義する 2 つの方法はあります。 使用することができます、 [ViewSelectedBy](./viewselectedby-element-format.md)するか、ビューのすべての定義を表示できるオブジェクトを定義する要素を使用できる、 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)によって表示されるオブジェクトを定義する要素、ビューの定義を特定します。 ほとんどの場合、ビューでは 1 つだけ定義は、オブジェクトは通常で定義されるため、 [ViewSelectedBy](./viewselectedby-element-format.md)要素。

次の例は、リスト ビューを使用して表示されるオブジェクトを定義する方法を示します、 [ViewSelectedBy](./viewselectedby-element-format.md)と[TypeName](./typename-element-for-viewselectedby-format.md)要素。 数に制限はありません[TypeName](./typename-element-for-viewselectedby-format.md)要素を指定できますが、およびその順序は重要ではありません。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

次の XML 要素を使用して、リスト ビューで使用されるオブジェクトを指定することができます。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。

- [TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .NET オブジェクトを指定します。 完全修飾 .NET 型名が必要です。 少なくとも 1 つの型またはビューの設定の選択範囲を指定する必要がありますが、指定できる要素の最大数はありません。

完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (Basic)](./list-view-basic.md)します。

次の例では、 [ViewSelectedBy](./viewselectedby-element-format.md)と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素。 関連する一連の同じオブジェクトのリスト ビューを定義する場合など、複数のビューおよびテーブル ビューを使用して表示されるオブジェクトがある選択範囲のセットを使用します。 選択範囲のセットを作成する方法の詳細については、次を参照してください。[選択範囲のセットを定義する](./defining-selection-sets.md)します。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

次の XML 要素を使用して、リスト ビューで使用されるオブジェクトを指定することができます。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、一連のビューで表示できるオブジェクトを指定します。 少なくとも 1 つの選択範囲のセットまたはビューの種類を指定する必要がありますが、指定できる要素の最大数はありません。

次の例は、特定の定義を使用してリスト ビューで表示されるオブジェクトを定義する方法を示します、 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素。 この要素を使用して、オブジェクト、オブジェクトの選択範囲のセットまたは定義を使用する場合を指定する選択条件の .NET 型名を指定できます。 選択条件を作成する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

リスト ビューの特定の定義で使用されるオブジェクトを指定する、次の XML 要素を使用できます。

- [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素定義によって表示されるオブジェクトを定義します。

- [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)要素を定義して表示されている .NET オブジェクトを指定します。 この要素を使用する場合は、完全修飾 .NET 型名が必要です。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。

- [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義で表示できるオブジェクトのセットを指定します。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。

- [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義を使用するのに必要な条件を指定します。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。 選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="displaying-groups-of-objects-in-a-list-view"></a>リスト ビューでオブジェクトのグループを表示します。

グループに、リスト ビューで表示されているオブジェクトを分離することができます。 限りませんグループを定義するだけで、特定のプロパティまたはスクリプトの値が変更されるたびに、その Windows PowerShell は新しいグループを開始します。 次の例で新しいグループが開始されるたびの値、 [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの変更。

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

次の XML 要素は、グループの開始時に定義に使用されます。

- [GroupBy](./groupby-element-for-view-format.md)プロパティまたは新しいグループを開始し、グループの表示方法を定義するスクリプト要素を定義します。

- [PropertyName](./propertyname-element-for-groupby-format.md)要素は、その値が変更されるたびに新しいグループを開始するプロパティを指定します。 プロパティまたはグループを開始するスクリプトを指定する必要がありますが、両方を指定することはできません。

- [ScriptBlock](./scriptblock-element-for-groupby-format.md)要素は、その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。 スクリプトまたはグループを開始するプロパティを指定する必要がありますが、両方を指定することはできません。

- [ラベル](./label-element-for-groupby-format.md)要素は、各グループの先頭に表示されるラベルを定義します。 この要素で指定されたテキスト、だけでなく Windows PowerShell には、新しいグループがトリガーされ、ラベルの前後に空白行を追加する値が表示されます。 この要素は省略可能です。

- [カスタム コントロール](./customcontrol-element-for-groupby-format.md)要素は、データを表示するために使用するコントロールを定義します。 この要素は省略可能です。

- [CustomControlName](./customcontrolname-element-for-groupby-format.md)要素は、一般的なを指定します。 または、データを表示するために使用するコントロールを表示します。 この要素は省略可能です。

グループを定義する完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (GroupBy)](./list-view-groupby.md)します。

## <a name="using-format-strings"></a>書式指定文字列を使用します。

さらに、データの表示方法を定義するビューには、書式設定文字列を追加できます。 次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

次の XML 要素を使用して、書式パターンを指定することができます。

- [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素は、ビューによって表示されるデータを指定します。

- [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素が値を持つが、ビューによって表示されるプロパティを指定します。 プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。

- [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md)要素は、ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。

- [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

次の例では、`ToString`スクリプトの値の書式設定メソッドが呼び出されます。 スクリプトでは、オブジェクトのすべてのメソッドを呼び出すことができます。 そのため、オブジェクトが、メソッドがなど`ToString`、書式設定パラメーターを持つ、スクリプトは、スクリプトの出力値の書式を指定するには、そのメソッドを呼び出すことができます。

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

次の XML 要素を呼び出すことができます、`ToString`メソッド。

- [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素は、ビューによって表示されるデータを指定します。

- [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)
