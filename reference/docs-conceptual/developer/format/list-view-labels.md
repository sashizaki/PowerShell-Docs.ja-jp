---
ms.date: 09/13/2016
ms.topic: reference
title: リスト ビュー (ラベル)
description: リスト ビュー (ラベル)
ms.openlocfilehash: 2d341ae95d025e0f95b5d88b96afb846b62b092f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666690"
---
# <a name="list-view-labels"></a><span data-ttu-id="055c0-103">リスト ビュー (ラベル)</span><span class="sxs-lookup"><span data-stu-id="055c0-103">List View (Labels)</span></span>

<span data-ttu-id="055c0-104">この例では、リストの各行にカスタムラベルを表示するリストビューを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="055c0-104">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="055c0-105">このリストビューには、Servicecontroller のプロパティが表示されます。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) [Get Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="055c0-105">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="055c0-106">リストビューのコンポーネントの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="055c0-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="055c0-107">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="055c0-107">To load this formatting file</span></span>

1. <span data-ttu-id="055c0-108">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="055c0-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="055c0-109">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="055c0-109">Save the text file.</span></span> <span data-ttu-id="055c0-110">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="055c0-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="055c0-111">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="055c0-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="055c0-112">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="055c0-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="055c0-113">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="055c0-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="055c0-114">対象</span><span class="sxs-lookup"><span data-stu-id="055c0-114">Demonstrates</span></span>

<span data-ttu-id="055c0-115">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="055c0-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="055c0-116">ビューの [Name](./name-element-for-view-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="055c0-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="055c0-117">ビューによって表示されるオブジェクトを定義する [Viewselectedby](./viewselectedby-element-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="055c0-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="055c0-118">ビューによって表示されるプロパティを定義する [ListControl](./listcontrol-element-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="055c0-118">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="055c0-119">リストビューの行に表示される内容を定義する [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="055c0-119">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="055c0-120">リストビューの行に表示される内容を定義する [Label](./label-element-for-listitem-for-listcontrol-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="055c0-120">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="055c0-121">表示されるプロパティを定義する [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="055c0-121">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="055c0-122">例</span><span class="sxs-lookup"><span data-stu-id="055c0-122">Example</span></span>

<span data-ttu-id="055c0-123">次の XML は、各行にカスタムラベルを表示するリストビューを定義しています。</span><span class="sxs-lookup"><span data-stu-id="055c0-123">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="055c0-124">この場合、ラベルには、各文字を大文字にしたプロパティ名と "property" という語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="055c0-124">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="055c0-125">各行には、プロパティの名前の後にプロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="055c0-125">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="055c0-126">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="055c0-126">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="055c0-127">参照</span><span class="sxs-lookup"><span data-stu-id="055c0-127">See Also</span></span>

[<span data-ttu-id="055c0-128">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="055c0-128">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="055c0-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="055c0-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
