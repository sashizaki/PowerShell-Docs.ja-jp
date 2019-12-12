---
title: リストビュー (基本) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 918f381c-43e6-4594-a468-a40bfa8a16d6
caps.latest.revision: 7
ms.openlocfilehash: 3c94d8e98f179286112a417230fce659dc0b614c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362811"
---
# <a name="list-view-basic"></a><span data-ttu-id="ded02-102">リスト ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="ded02-102">List View (Basic)</span></span>

<span data-ttu-id="ded02-103">この例では、Servicecontroller を表示する基本的なリストビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) [Get Service](/powershell/module/microsoft.powershell.management/get-service)コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded02-103">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="ded02-104">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ded02-104">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="ded02-105">この書式設定ファイルを読み込むには</span><span class="sxs-lookup"><span data-stu-id="ded02-105">To load this formatting file</span></span>

1. <span data-ttu-id="ded02-106">このトピックの「例」のセクションにある XML をテキストファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ded02-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="ded02-107">テキスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ded02-107">Save the text file.</span></span> <span data-ttu-id="ded02-108">`format.ps1xml` 拡張機能をファイルに追加して、フォーマットファイルとして識別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ded02-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="ded02-109">Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込みます: `Update-formatdata -prependpath PathToFormattingFile`。</span><span class="sxs-lookup"><span data-stu-id="ded02-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="ded02-110">この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="ded02-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="ded02-111">コマンドレットの実行時には `prependPath` パラメーターを使用する必要があり、このフォーマットファイルをモジュールとして読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="ded02-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ded02-112">使用例</span><span class="sxs-lookup"><span data-stu-id="ded02-112">Demonstrates</span></span>

<span data-ttu-id="ded02-113">この書式設定ファイルは、次の XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="ded02-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="ded02-114">ビューの[Name](./name-element-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="ded02-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="ded02-115">ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="ded02-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="ded02-116">ビューによって表示されるプロパティを定義する[ListControl](./listcontrol-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="ded02-116">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="ded02-117">リストビューの行に表示される内容を定義する[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="ded02-117">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="ded02-118">表示されるプロパティを定義する[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="ded02-118">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="ded02-119">例</span><span class="sxs-lookup"><span data-stu-id="ded02-119">Example</span></span>

<span data-ttu-id="ded02-120">次の XML は、Servicecontroller の4つのプロパティを表示するリストビューを定義しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ded02-120">The following XML defines a list view that displays four properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="ded02-121">各行には、プロパティの名前の後にプロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ded02-121">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="ded02-122">次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。</span><span class="sxs-lookup"><span data-stu-id="ded02-122">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ded02-123">参照</span><span class="sxs-lookup"><span data-stu-id="ded02-123">See Also</span></span>

[<span data-ttu-id="ded02-124">フォーマットファイルの例</span><span class="sxs-lookup"><span data-stu-id="ded02-124">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="ded02-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ded02-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
