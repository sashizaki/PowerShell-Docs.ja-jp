---
ms.date: 09/13/2016
ms.topic: reference
title: リスト ビュー (基本)
description: リスト ビュー (基本)
ms.openlocfilehash: d80ac9c6143b976d8bc13e2b184e4f5a2f8a37ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666639"
---
# <a name="list-view-basic"></a><span data-ttu-id="c12a6-103">リスト ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="c12a6-103">List View (Basic)</span></span>

<span data-ttu-id="c12a6-104">この例では、Servicecontroller を表示する基本的なリストビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) [Get Service](/powershell/module/microsoft.powershell.management/get-service) コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c12a6-104">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="c12a6-105">リストビューのコンポーネントの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a6-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="c12a6-106">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="c12a6-106">To load this formatting file</span></span>

1. <span data-ttu-id="c12a6-107">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c12a6-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="c12a6-108">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c12a6-108">Save the text file.</span></span> <span data-ttu-id="c12a6-109">ファイルに拡張子を追加して、 `format.ps1xml` 書式設定ファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c12a6-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="c12a6-110">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込み `Update-formatdata -prependpath PathToFormattingFile` ます。</span><span class="sxs-lookup"><span data-stu-id="c12a6-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="c12a6-111">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="c12a6-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="c12a6-112">`prependPath`コマンドレットを実行するときにパラメーターを使用する必要があります。このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="c12a6-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c12a6-113">対象</span><span class="sxs-lookup"><span data-stu-id="c12a6-113">Demonstrates</span></span>

<span data-ttu-id="c12a6-114">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="c12a6-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="c12a6-115">ビューの [Name](./name-element-for-view-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="c12a6-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="c12a6-116">ビューによって表示されるオブジェクトを定義する [Viewselectedby](./viewselectedby-element-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="c12a6-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="c12a6-117">ビューによって表示されるプロパティを定義する [ListControl](./listcontrol-element-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="c12a6-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="c12a6-118">リストビューの行に表示される内容を定義する [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="c12a6-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="c12a6-119">表示されるプロパティを定義する [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="c12a6-119">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="c12a6-120">例</span><span class="sxs-lookup"><span data-stu-id="c12a6-120">Example</span></span>

<span data-ttu-id="c12a6-121">次の XML は、Servicecontroller の4つのプロパティを表示するリストビューを定義しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c12a6-121">The following XML defines a list view that displays four properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="c12a6-122">各行には、プロパティの名前の後にプロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c12a6-122">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="c12a6-123">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="c12a6-123">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c12a6-124">参照</span><span class="sxs-lookup"><span data-stu-id="c12a6-124">See Also</span></span>

[<span data-ttu-id="c12a6-125">書式設定ファイルの例</span><span class="sxs-lookup"><span data-stu-id="c12a6-125">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="c12a6-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="c12a6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
