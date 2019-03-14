---
title: リスト ビュー (Basic) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 918f381c-43e6-4594-a468-a40bfa8a16d6
caps.latest.revision: 7
ms.openlocfilehash: 3c94d8e98f179286112a417230fce659dc0b614c
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794163"
---
# <a name="list-view-basic"></a>リスト ビュー (基本)

この例は、基本のリストに表示するビューを実装する方法を示します、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)によって返されるオブジェクト、 [Get-service](/powershell/module/microsoft.powershell.management/get-service)コマンドレット。 リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

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

- [ListControl](./listcontrol-element-format.md)どのようなプロパティを表示するビューを定義する要素。

- [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)リスト ビューの行に表示される内容を定義する要素。

- [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)表示するプロパティを定義する要素。

## <a name="example"></a>例

次の XML の 4 つのプロパティを表示するリスト ビューの定義、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。 各行の後に、プロパティの値、プロパティの名前が表示されます。

```xml
<Configuration>
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
</Configuration>
```

次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)このフォーマット ファイルが読み込まれた後のオブジェクトします。

```powershell
Get-Service f*
```

```output
Name        : Fax
DisplayName : Fax
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
Status      : Running
ServiceType : Win32OwnProcess

Name        : fdPHost
DisplayName : Function Discovery Provider Host
Status      : Stopped
ServiceType : Win32ShareProcess

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
Status      : Running
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
Status      : Running
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a>参照

[書式設定ファイルの例](./examples-of-formatting-files.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
