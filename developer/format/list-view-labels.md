---
title: リスト ビュー (ラベル) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53442bb1-74a3-49f9-9150-3bc3081a7565
caps.latest.revision: 6
ms.openlocfilehash: 2bb62ab3e4fa1db9b3af8c82eb9035aa4f3e31c0
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860128"
---
# <a name="list-view-labels"></a>リスト ビュー (ラベル)

この例では、一覧の行ごとのカスタム ラベルを表示するリスト ビューを実装する方法を示します。 このリスト ビューのプロパティを表示する、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトによって返される、 [Get-service](/powershell/module/microsoft.powershell.management/get-service)コマンドレット。 リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。
この例では、一覧の行ごとのカスタム ラベルを表示するリスト ビューを実装する方法を示します。 このリスト ビューのプロパティを表示する、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトによって返される、 [Get-service](/powershell/module/Microsoft.PowerShell.Management/Get-Service)コマンドレット。 リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

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

- [ラベル](./label-element-for-listitem-for-listcontrol-format.md)リスト ビューの行に表示される内容を定義する要素。

- [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)表示するプロパティを定義する要素。

## <a name="example"></a>例

次の XML では、行ごとにカスタム ラベルを表示するリスト ビューを定義します。 この場合、ラベルには、それぞれの文字を大文字で入力、プロパティ名と"property"という単語が含まれます。 各行の後に、プロパティの値、プロパティの名前が表示されます。

```xml
<Configuration>
  <ViewDefinitions>
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
            <Label>NAME property</Label>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <Label>DISPLAYNAME property</Label>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <Label>STATUS property</Label>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <Label>SERVICETYPE property</Label>
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

次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)このフォーマット ファイルが読み込まれた後のオブジェクトします。

```powershell
Get-Service f*
```

```output
NAME property        : Fax
DISPLAYNAME property : Fax
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FCSAM
DISPLAYNAME property : Microsoft Antimalware Service
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : fdPHost
DISPLAYNAME property : Function Discovery Provider Host
STATUS property      : Stopped
SERVICETYPE property : Win32ShareProcess

NAME property        : FDResPub
DISPLAYNAME property : Function Discovery Resource Publication
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache
DISPLAYNAME property : Windows Font Cache Service
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache3.0.0.0
DISPLAYNAME property : Windows Presentation Foundation Font Cache 3.0.0.0
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FSysAgent
DISPLAYNAME property : Microsoft Forefront System Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : FwcAgent
DISPLAYNAME property : Firewall Client Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess
```

## <a name="see-also"></a>参照

[書式設定ファイルの例](./examples-of-formatting-files.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
