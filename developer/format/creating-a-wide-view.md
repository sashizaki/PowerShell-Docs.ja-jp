---
title: ワイド ビューを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4303c5-b451-4ccb-9831-b17a17ceac20
caps.latest.revision: 16
ms.openlocfilehash: 651de5d3bc2619f20438f3951ac5a8c4b0bf46d4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066721"
---
# <a name="creating-a-wide-view"></a>ワイド ビューを作成する

全体のビューには、表示される各オブジェクトの単一の値が表示されます。 表示される値には、.NET オブジェクトのプロパティの値またはスクリプトの値を指定できます。 既定ではありませんラベルまたはこのビューのヘッダーです。

## <a name="a-wide-view-display"></a>表示幅が広い表示

次の例は、Windows PowerShell を表示する方法を示しています、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクトによって返される、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットの出力がパイプを使用するとき、 [Format-wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide)コマンドレット。 (既定で、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは、テーブル ビューを返します)。この例では、2 つの列が返された各オブジェクトのプロセスの名前を表示に使用されます。 オブジェクトのプロパティの名前が表示されないプロパティの値のみです。

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a>ワイド ビューを定義します。

次の XML の表示幅が広いスキーマを示しています、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

次の XML 要素は、ワイド ビュー定義に使用されます。

- [ビュー](./view-element-format.md)要素は、ワイド ビューの親要素です。 (これは、テーブル、リスト、およびカスタムのコントロール ビューに、同じ親要素です)。

- [名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します。 この要素は、すべてのビューに必要です。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。 この要素が必要です。

- [GroupBy](./groupby-element-for-view-format.md)オブジェクトの新しいグループが表示される要素を定義します。 特定のプロパティまたはスクリプトの値が変更されるたびに新しいグループが開始されます。 この要素は省略可能です。

- [コントロール](./controls-element-for-view-format.md)要素は、ワイド ビューで定義されているカスタム コントロールを定義します。 コントロールでは、さらに、データの表示方法を指定する方法を提供します。 この要素は省略可能です。 ビューがその独自のカスタム コントロールを定義できます。 または書式設定ファイルに任意のビューで使用できる一般的なコントロールを使用できます。 カスタム コントロールの詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。

- [WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。 前の例では、表示するビューを設計、 [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName)プロパティ。

単純なワイド ビューを定義する完全な書式設定ファイルの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

## <a name="providing-definitions-for-your-wide-view"></a>ワイド ビューの定義を提供します。

ワイド ビューの子要素を使用して、1 つまたは複数の定義を提供することができます、 [WideControl](./widecontrol-element-format.md)要素。 通常、ビューには、1 つだけ定義があります。 ビューでの値を表示する 1 つの定義は、次の例では、 [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName)プロパティ。 ワイド ビューには、プロパティの値またはスクリプト (この例では表示されません) の値を表示できます。

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

次の XML 要素は、ワイド ビューの定義を使用できます。

- [WideControl](./widecontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。

- [AutoSize](./autosize-element-for-widecontrol-format.md)要素は、かどうか、列のサイズと列の数が調整のデータのサイズを指定します。 この要素は省略可能です。

- [ColumnNumber](./columnnumber-element-for-widecontrol-format.md)要素をワイド ビューに表示される列の数を指定します。 この要素は省略可能です。

- [WideEntries](./wideentries-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。 ほとんどの場合、ビューは 1 つだけ定義になります。 この要素が必要です。

- [WideEntry](./wideentry-element-for-widecontrol-format.md)要素は、ビューの定義を提供します。 少なくとも 1 つ[WideEntry](./wideentry-element-for-widecontrol-format.md)が必要です。 ただし、追加できる要素の数に上限はありません。 ほとんどの場合、ビューは 1 つだけ定義になります。

- [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。 この要素は省略可能と複数を定義する場合にのみ必要です[WideEntry](./wideentry-element-for-widecontrol-format.md)さまざまなオブジェクトを表示する要素。

- [WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。 他の種類のビューとは対照的ワイド コントロールは、1 つの項目を表示できます。

- [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素が値を持つが、ビューによって表示されるプロパティを指定します。 プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。

- [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md)要素は、ビューによって表示される値を持つスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

- [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、データを表示するために使用するパターンを指定します。 この要素は省略可能です。

表示幅が広い定義を定義する完全な書式設定ファイルの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

## <a name="defining-the-objects-that-use-the-wide-view"></a>表示幅が広いを使用するオブジェクトを定義します。

.NET オブジェクトを使用して、表示幅が広いを定義する 2 つの方法はあります。 使用することができます、 [ViewSelectedBy](./viewselectedby-element-format.md)するか、ビューのすべての定義を表示できるオブジェクトを定義する要素を使用できる、 [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)によって表示されるオブジェクトを定義する要素、ビューの定義を特定します。 ほとんどの場合、ビューでは 1 つだけ定義は、オブジェクトは通常で定義されるため、 [ViewSelectedBy](./viewselectedby-element-format.md)要素。

次の例は、表示幅が広いを使用して表示されるオブジェクトを定義する方法を示します、 [ViewSelectedBy](./viewselectedby-element-format.md)と[TypeName](./typename-element-for-viewselectedby-format.md)要素。 数に制限はありません[TypeName](./typename-element-for-viewselectedby-format.md)要素を指定できますが、およびその順序は重要ではありません。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

表示幅が広いによって使用されるオブジェクトを指定する、次の XML 要素を使用できます。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素は、ワイド ビューによって表示されるオブジェクトを定義します。

- [TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される、.NET を指定します。 完全修飾 .NET 型名が必要です。 少なくとも 1 つの型またはビューの設定の選択範囲を指定する必要がありますが、指定できる要素の最大数はありません。

完全な書式設定ファイルの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

次の例では、 [ViewSelectedBy](./viewselectedby-element-format.md)と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素。 関連する一連のワイド ビューを定義する場合など、複数のビューおよびテーブル ビューを使用して、同じオブジェクトに対して表示されるオブジェクトがある選択範囲のセットを使用します。 選択範囲のセットを作成する方法の詳細については、次を参照してください。[選択範囲のセットを定義する](./defining-selection-sets.md)します。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

表示幅が広いによって使用されるオブジェクトを指定する、次の XML 要素を使用できます。

- [ViewSelectedBy](./viewselectedby-element-format.md)要素は、ワイド ビューによって表示されるオブジェクトを定義します。

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、一連のビューで表示できるオブジェクトを指定します。 少なくとも 1 つの選択範囲のセットまたはビューの種類を指定する必要がありますが、指定できる要素の最大数はありません。

次の例は、特定の定義を使用して、表示幅が広いで表示されるオブジェクトを定義する方法を示します、 [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)要素。 この要素を使用して、オブジェクト、オブジェクトの選択範囲のセットまたは定義を使用する場合を指定する選択条件の .NET 型名を指定できます。 選択条件を作成する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

表示幅が広いの特定の定義で使用されるオブジェクトを指定する、次の XML 要素を使用できます。

- [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md)要素定義によって表示されるオブジェクトを定義します。

- [TypeName](./typename-element-for-viewselectedby-format.md)要素を定義して表示される .NET を指定します。 この要素を使用する場合は、完全修飾 .NET 型名が必要です。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) (表示されない) 要素は、この定義で表示できるオブジェクトのセットを指定します。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。

- [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) (表示されない) 要素は、この定義を使用するのに必要な条件を指定します。 少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。 選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="displaying-groups-of-objects-in-a-wide-view"></a>ワイド ビューでオブジェクトのグループを表示します。

グループにワイド ビューによって表示されるオブジェクトを分離することができます。 限りませんグループを定義するだけで、特定のプロパティまたはスクリプトの値が変更されるたびに、その Windows PowerShell は新しいグループを開始します。 次の例で新しいグループが開始されるたびの値、 [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの変更。

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

グループを定義する完全な書式設定ファイルの例は、次を参照してください。[表示幅が広い (GroupBy)](./wide-view-groupby.md)します。

## <a name="using-format-strings"></a>書式指定文字列を使用します。

さらに、データの表示方法を定義するワイド ビューには、書式設定文字列を追加できます。 次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

次の XML 要素を使用して、書式パターンを指定することができます。

- [WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。

- [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md)要素が値を持つが、ビューによって表示されるプロパティを指定します。 プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。

- [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md)要素は、ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します

- [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

次の例では、`ToString`スクリプトの値の書式設定メソッドが呼び出されます。 スクリプトでは、オブジェクトのすべてのメソッドを呼び出すことができます。 そのため、オブジェクトが、メソッドがなど`ToString`、書式設定パラメーターを持つ、スクリプトは、スクリプトの出力値の書式を指定するには、そのメソッドを呼び出すことができます。

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

次の XML 要素を呼び出すことができます、`ToString`メソッド。

- [WideItem](./wideitem-element-for-widecontrol-format.md)要素は、ビューによって表示されるデータを指定します。

- [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。 スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。

## <a name="see-also"></a>参照

[表示幅が広い (Basic)](./wide-view-basic.md)

[表示幅が広い (GroupBy)](./wide-view-groupby.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
