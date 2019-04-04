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
ms.openlocfilehash: 27de41c88e224f7610c10a764e51524016ecc8cb
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794826"
---
# <a name="list-view-labels"></a><span data-ttu-id="8b299-102">リスト ビュー (ラベル)</span><span class="sxs-lookup"><span data-stu-id="8b299-102">List View (Labels)</span></span>

<span data-ttu-id="8b299-103">この例では、一覧の行ごとのカスタム ラベルを表示するリスト ビューを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8b299-103">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="8b299-104">このリスト ビューのプロパティを表示する、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトによって返される、 [Get-service](/powershell/module/Microsoft.PowerShell.Management/Get-Service)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="8b299-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="8b299-105">リスト ビューのコンポーネントに関する詳細については、[リスト ビューを作成する](./creating-a-list-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b299-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="8b299-106">この書式設定ファイルを読み込む</span><span class="sxs-lookup"><span data-stu-id="8b299-106">To load this formatting file</span></span>

1. <span data-ttu-id="8b299-107">このトピックの例のセクションからテキスト ファイルに XML をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8b299-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="8b299-108">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="8b299-108">Save the text file.</span></span> <span data-ttu-id="8b299-109">追加してください、`format.ps1xml`書式設定ファイルとして識別するファイルへの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="8b299-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="8b299-110">Windows PowerShell を開き、現在のセッションに書式設定ファイルを読み込むには、次のコマンドを実行します。`Update-formatdata -prependpath PathToFormattingFile`します。</span><span class="sxs-lookup"><span data-stu-id="8b299-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="8b299-111">この書式設定ファイルは、Windows PowerShell の書式設定ファイルで既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b299-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="8b299-112">使用する必要があります、`prependPath`をモジュールとしてファイルのパラメーター、コマンドレットを実行すると、この書式設定を読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="8b299-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="8b299-113">使用例</span><span class="sxs-lookup"><span data-stu-id="8b299-113">Demonstrates</span></span>

<span data-ttu-id="8b299-114">この書式設定ファイルには、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b299-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="8b299-115">[名前](./name-element-for-view-format.md)ビューの要素。</span><span class="sxs-lookup"><span data-stu-id="8b299-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="8b299-116">[ViewSelectedBy](./viewselectedby-element-format.md)どのようなオブジェクトはビューで表示を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="8b299-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="8b299-117">[ListControl](./listcontrol-element-format.md)どのようなプロパティを表示するビューを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="8b299-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="8b299-118">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)リスト ビューの行に表示される内容を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="8b299-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="8b299-119">[ラベル](./label-element-for-listitem-for-listcontrol-format.md)リスト ビューの行に表示される内容を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="8b299-119">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="8b299-120">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)表示するプロパティを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="8b299-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="8b299-121">例</span><span class="sxs-lookup"><span data-stu-id="8b299-121">Example</span></span>

<span data-ttu-id="8b299-122">次の XML では、行ごとにカスタム ラベルを表示するリスト ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b299-122">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="8b299-123">この場合、ラベルには、それぞれの文字を大文字で入力、プロパティ名と"property"という単語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b299-123">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="8b299-124">各行の後に、プロパティの値、プロパティの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b299-124">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="8b299-125">次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)このフォーマット ファイルが読み込まれた後のオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="8b299-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8b299-126">参照</span><span class="sxs-lookup"><span data-stu-id="8b299-126">See Also</span></span>

[<span data-ttu-id="8b299-127">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="8b299-127">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="8b299-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="8b299-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
