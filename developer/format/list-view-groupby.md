---
title: リスト ビュー (GroupBy) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2e66c86-83a7-4148-8575-c28d6d429d4f
caps.latest.revision: 6
ms.openlocfilehash: c178c4a48f9595001bcc249d5f55886fa54bb9f2
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794446"
---
# <a name="list-view-groupby"></a>リスト ビュー (グループ別)

この例では、一覧の行をグループに分割するリスト ビューを実装する方法を示します。 このリスト ビューのプロパティを表示する、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)によって返されるオブジェクト、 [Get-service](/powershell/module/Microsoft.PowerShell.Management/Get-Service)コマンドレット。 リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

### <a name="to-load-this-formatting-file"></a>この書式設定ファイルを読み込む

1. このトピックの例のセクションからテキスト ファイルに XML をコピーします。

2. テキスト ファイルを保存します。 追加してください、`format.ps1xml`書式設定ファイルとして識別するファイルへの拡張機能。

3. Windows PowerShell を開き、現在のセッションに書式設定ファイルを読み込むには、次のコマンドを実行します。`Update-formatdata -prependpath PathToFormattingFile`します。

   > [!WARNING]
   > この書式設定ファイルは、Windows PowerShell の書式設定ファイルで既に定義されているオブジェクトの表示を定義します。 使用する必要があります、`prependPath`をモジュールとしてファイルのパラメーター、コマンドレットを実行すると、この書式設定を読み込むことができません。

## <a name="demonstrates"></a>使用例

この書式設定ファイルには、次の XML 要素を示しています。

- [名前](./name-element-for-view-format.md)ビューの要素。

- [ViewSelectedBy](./viewselectedby-element-format.md)どのようなオブジェクトはビューで表示を定義する要素。

- [GroupBy](./viewselectedby-element-format.md)オブジェクトの新しいグループを表示する方法を定義する要素。

- [ListControl](./listcontrol-element-format.md)どのようなプロパティを表示するビューを定義する要素。

- [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)リスト ビューの行に表示される内容を定義する要素。

- [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)表示するプロパティを定義する要素。

## <a name="example"></a>例

次の XML を新しいを開始するリスト ビューを定義するたびにグループ化の値、 [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status)プロパティの変更。 各グループが開始されると、プロパティの新しい値を含むカスタム ラベルが表示されます。

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
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
                <PropertyName>ServiceType</PropertyName>
              </ListItem>
            </ListItems>
          </ListEntry>
        </ListEntries>
      </ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)このフォーマット ファイルが読み込まれた後のオブジェクトします。 追加する前に、グループのラベルの後の空白行は、Windows PowerShell によって自動的に追加されます。

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a>参照

[書式設定ファイルの例](./examples-of-formatting-files.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
