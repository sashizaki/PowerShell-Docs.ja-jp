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
ms.openlocfilehash: ad7ea457fe0f67bfa41f6bf81f36d4b2e4a76cb3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860148"
---
# <a name="list-view-groupby"></a><span data-ttu-id="62889-102">リスト ビュー (グループ別)</span><span class="sxs-lookup"><span data-stu-id="62889-102">List View (GroupBy)</span></span>

<span data-ttu-id="62889-103">この例では、一覧の行をグループに分割するリスト ビューを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="62889-103">This example shows how to implement a list view that separates the rows of the list into groups.</span></span> <span data-ttu-id="62889-104">このリスト ビューのプロパティを表示する、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)によって返されるオブジェクト、 [Get-service](/powershell/module/microsoft.powershell.management/get-service)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="62889-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="62889-105">リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="62889-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>
<span data-ttu-id="62889-106">この例では、一覧の行をグループに分割するリスト ビューを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="62889-106">This example shows how to implement a list view that separates the rows of the list into groups.</span></span> <span data-ttu-id="62889-107">このリスト ビューのプロパティを表示する、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)によって返されるオブジェクト、 [Get-service](/powershell/module/Microsoft.PowerShell.Management/Get-Service)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="62889-107">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="62889-108">リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="62889-108">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="62889-109">この書式設定ファイルを読み込む</span><span class="sxs-lookup"><span data-stu-id="62889-109">To load this formatting file</span></span>

1. <span data-ttu-id="62889-110">このトピックの例のセクションからテキスト ファイルに XML をコピーします。</span><span class="sxs-lookup"><span data-stu-id="62889-110">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="62889-111">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="62889-111">Save the text file.</span></span> <span data-ttu-id="62889-112">追加してください、`format.ps1xml`書式設定ファイルとして識別するファイルへの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="62889-112">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="62889-113">Windows PowerShell を開き、現在のセッションに書式設定ファイルを読み込むには、次のコマンドを実行します。`Update-formatdata -prependpath PathToFormattingFile`します。</span><span class="sxs-lookup"><span data-stu-id="62889-113">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="62889-114">この書式設定ファイルは、Windows PowerShell の書式設定ファイルで既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="62889-114">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="62889-115">使用する必要があります、`prependPath`をモジュールとしてファイルのパラメーター、コマンドレットを実行すると、この書式設定を読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="62889-115">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="62889-116">使用例</span><span class="sxs-lookup"><span data-stu-id="62889-116">Demonstrates</span></span>

<span data-ttu-id="62889-117">この書式設定ファイルには、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="62889-117">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="62889-118">[名前](./name-element-for-view-format.md)ビューの要素。</span><span class="sxs-lookup"><span data-stu-id="62889-118">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="62889-119">[ViewSelectedBy](./viewselectedby-element-format.md)どのようなオブジェクトはビューで表示を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="62889-119">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="62889-120">[GroupBy](./viewselectedby-element-format.md)オブジェクトの新しいグループを表示する方法を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="62889-120">The [GroupBy](./viewselectedby-element-format.md) element that defines how a new group of objects is displayed.</span></span>

- <span data-ttu-id="62889-121">[ListControl](./listcontrol-element-format.md)どのようなプロパティを表示するビューを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="62889-121">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="62889-122">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)リスト ビューの行に表示される内容を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="62889-122">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="62889-123">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)表示するプロパティを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="62889-123">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="62889-124">例</span><span class="sxs-lookup"><span data-stu-id="62889-124">Example</span></span>

<span data-ttu-id="62889-125">次の XML を新しいを開始するリスト ビューを定義するたびにグループ化の値、 [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status)プロパティの変更。</span><span class="sxs-lookup"><span data-stu-id="62889-125">The following XML defines a list view that starts a new group whenever the value of the [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status) property changes.</span></span> <span data-ttu-id="62889-126">各グループが開始されると、プロパティの新しい値を含むカスタム ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62889-126">When each group is started, a custom label is displayed that includes the new value of the property.</span></span>

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

<span data-ttu-id="62889-127">次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)このフォーマット ファイルが読み込まれた後のオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="62889-127">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span> <span data-ttu-id="62889-128">追加する前に、グループのラベルの後の空白行は、Windows PowerShell によって自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="62889-128">The blank lines added before and after the group label are automatically added by Windows PowerShell.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="62889-129">参照</span><span class="sxs-lookup"><span data-stu-id="62889-129">See Also</span></span>

[<span data-ttu-id="62889-130">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="62889-130">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="62889-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="62889-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
