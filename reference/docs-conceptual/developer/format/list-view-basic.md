---
title: リストビュー (基本) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74ff8f6eee0a9358c123455aa00736a11e7f085d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783553"
---
# <a name="list-view-basic"></a><span data-ttu-id="4efca-102">リスト ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="4efca-102">List View (Basic)</span></span>

<span data-ttu-id="4efca-103">この例では、Servicecontroller を表示する基本的なリストビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) [Get Service](/powershell/module/microsoft.powershell.management/get-service)コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4efca-103">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="4efca-104">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4efca-104">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="4efca-105">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="4efca-105">To load this formatting file</span></span>

1. <span data-ttu-id="4efca-106">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4efca-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="4efca-107">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4efca-107">Save the text file.</span></span> <span data-ttu-id="4efca-108">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4efca-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="4efca-109">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="4efca-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4efca-110">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="4efca-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="4efca-111">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="4efca-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4efca-112">対象</span><span class="sxs-lookup"><span data-stu-id="4efca-112">Demonstrates</span></span>

<span data-ttu-id="4efca-113">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="4efca-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="4efca-114">ビューの[Name](./name-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4efca-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="4efca-115">ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4efca-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="4efca-116">ビューによって表示されるプロパティを定義する[ListControl](./listcontrol-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4efca-116">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="4efca-117">リストビューの行に表示される内容を定義する[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4efca-117">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="4efca-118">表示されるプロパティを定義する[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4efca-118">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="4efca-119">例</span><span class="sxs-lookup"><span data-stu-id="4efca-119">Example</span></span>

<span data-ttu-id="4efca-120">次の XML は、Servicecontroller の4つのプロパティを表示するリストビューを定義しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4efca-120">The following XML defines a list view that displays four properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="4efca-121">各行には、プロパティの名前の後にプロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4efca-121">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="4efca-122">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="4efca-122">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4efca-123">参照</span><span class="sxs-lookup"><span data-stu-id="4efca-123">See Also</span></span>

[<span data-ttu-id="4efca-124">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="4efca-124">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="4efca-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4efca-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
