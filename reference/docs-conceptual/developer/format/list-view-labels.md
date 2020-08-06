---
title: リストビュー (ラベル) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: da45bd8dce7ac2149de6a34c11d5419d6cb4ddb0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773387"
---
# <a name="list-view-labels"></a><span data-ttu-id="0fa1a-102">リスト ビュー (ラベル)</span><span class="sxs-lookup"><span data-stu-id="0fa1a-102">List View (Labels)</span></span>

<span data-ttu-id="0fa1a-103">この例では、リストの各行にカスタムラベルを表示するリストビューを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-103">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="0fa1a-104">このリストビューには、Servicecontroller のプロパティが表示されます。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) [Get Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service)コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="0fa1a-105">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="0fa1a-106">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="0fa1a-106">To load this formatting file</span></span>

1. <span data-ttu-id="0fa1a-107">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="0fa1a-108">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-108">Save the text file.</span></span> <span data-ttu-id="0fa1a-109">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="0fa1a-110">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="0fa1a-111">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="0fa1a-112">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="0fa1a-113">対象</span><span class="sxs-lookup"><span data-stu-id="0fa1a-113">Demonstrates</span></span>

<span data-ttu-id="0fa1a-114">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="0fa1a-115">ビューの[Name](./name-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="0fa1a-116">ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="0fa1a-117">ビューによって表示されるプロパティを定義する[ListControl](./listcontrol-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="0fa1a-118">リストビューの行に表示される内容を定義する[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="0fa1a-119">リストビューの行に表示される内容を定義する[Label](./label-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-119">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="0fa1a-120">表示されるプロパティを定義する[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="0fa1a-121">例</span><span class="sxs-lookup"><span data-stu-id="0fa1a-121">Example</span></span>

<span data-ttu-id="0fa1a-122">次の XML は、各行にカスタムラベルを表示するリストビューを定義しています。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-122">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="0fa1a-123">この場合、ラベルには、各文字を大文字にしたプロパティ名と "property" という語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-123">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="0fa1a-124">各行には、プロパティの名前の後にプロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-124">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="0fa1a-125">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0fa1a-126">参照</span><span class="sxs-lookup"><span data-stu-id="0fa1a-126">See Also</span></span>

[<span data-ttu-id="0fa1a-127">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="0fa1a-127">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="0fa1a-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="0fa1a-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
