---
title: リスト ビューの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c7a40ca-1786-46f0-bab5-6ce229daa7ee
caps.latest.revision: 14
ms.openlocfilehash: 25d24063501196d44e0f806a55bb699c82f771ce
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066857"
---
# <a name="creating-a-list-view"></a><span data-ttu-id="c54a2-102">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="c54a2-102">Creating a List View</span></span>

<span data-ttu-id="c54a2-103">リスト ビューでは、(順番に) に 1 つの列のデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-103">A list view displays data in a single column (in sequential order).</span></span> <span data-ttu-id="c54a2-104">一覧に表示されるデータには、.NET プロパティの値またはスクリプトの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-104">The data displayed in the list can be the value of a .NET property or the value of a script.</span></span>

## <a name="a-list-view-display"></a><span data-ttu-id="c54a2-105">リスト ビューの表示</span><span class="sxs-lookup"><span data-stu-id="c54a2-105">A List View Display</span></span>

<span data-ttu-id="c54a2-106">次の出力は、Windows PowerShell でのプロパティを表示する方法を示しています。 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトによって返される、 [Get-service](/powershell/module/microsoft.powershell.management/get-service)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="c54a2-106">The following output shows how Windows PowerShell displays the properties of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects that are returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="c54a2-107">この例では、前のオブジェクトからの空白行で区切られた各オブジェクトに、3 つのオブジェクトは返されました。</span><span class="sxs-lookup"><span data-stu-id="c54a2-107">In this example, three objects were returned, with each object separated from the preceding object by a blank line.</span></span>

```powershell
Get-Service | format-list
```

```output
Name                : AEADIFilters
DisplayName         : Andrea ADI Filters Service
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess

Name                : AeLookupSvc
DisplayName         : Application Experience
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32ShareProcess

Name                : AgereModemAudio
DisplayName         : Agere Modem Call Progress Audio
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess
...
```

## <a name="defining-the-list-view"></a><span data-ttu-id="c54a2-108">リスト ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-108">Defining the List View</span></span>

<span data-ttu-id="c54a2-109">次の XML は、リスト ビューのスキーマのいくつかのプロパティを表示するため、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c54a2-109">The following XML shows the list view schema for displaying several properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="c54a2-110">リスト ビューで表示する各プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c54a2-110">You must specify each property that you want displayed in the list view.</span></span>

```xml
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
```

<span data-ttu-id="c54a2-111">次の XML 要素は、リスト ビューの定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-111">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="c54a2-112">[ビュー](./view-element-format.md)要素はリスト ビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-112">The [View](./view-element-format.md) element is the parent element of the list view.</span></span> <span data-ttu-id="c54a2-113">(これは、テーブル、ビューの幅をカスタム コントロールの同じ親要素です)。</span><span class="sxs-lookup"><span data-stu-id="c54a2-113">(This is the same parent element for the table, wide, and custom control views.)</span></span>

- <span data-ttu-id="c54a2-114">[名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-114">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="c54a2-115">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-115">This element is required for all views.</span></span>

- <span data-ttu-id="c54a2-116">[ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="c54a2-117">この要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-117">This element is required.</span></span>

- <span data-ttu-id="c54a2-118">[GroupBy](./groupby-element-for-view-format.md)オブジェクトの新しいグループが表示される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-118">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="c54a2-119">特定のプロパティまたはスクリプトの値が変更されるたびに新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-119">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="c54a2-120">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-120">This element is optional.</span></span>

- <span data-ttu-id="c54a2-121">[コントロール](./controls-element-for-view-format.md)要素がリスト ビューで定義されているカスタム コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-121">The [Controls](./controls-element-for-view-format.md) element defines the custom controls that are defined by the list view.</span></span> <span data-ttu-id="c54a2-122">コントロールでは、さらに、データの表示方法を指定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-122">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="c54a2-123">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-123">This element is optional.</span></span> <span data-ttu-id="c54a2-124">ビューがその独自のカスタム コントロールを定義できます。 または書式設定ファイルに任意のビューで使用できる一般的なコントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-124">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="c54a2-125">カスタム コントロールの詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-125">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="c54a2-126">[ListControl](./listcontrol-element-format.md)要素は、ビューに表示される内容と書式設定方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-126">The [ListControl](./listcontrol-element-format.md) element defines what is displayed in the view and how it is formatted.</span></span> <span data-ttu-id="c54a2-127">その他のすべてのビューと同様に、リスト ビューを表示できますオブジェクトのプロパティの値またはスクリプトによって生成された値。</span><span class="sxs-lookup"><span data-stu-id="c54a2-127">Similar to all other views, a list view can display the values of object properties or values generated by script.</span></span>

<span data-ttu-id="c54a2-128">単純なリスト ビューを定義する完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (Basic)](./list-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-128">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-list-view"></a><span data-ttu-id="c54a2-129">リスト ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-129">Providing Definitions for Your List View</span></span>

<span data-ttu-id="c54a2-130">リスト ビューには、子要素を使用して 1 つまたは複数の定義ができるように、 [ListControl](./listcontrol-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c54a2-130">List views can provide one or more definitions by using the child elements of the [ListControl](./listcontrol-element-format.md) element.</span></span> <span data-ttu-id="c54a2-131">通常、ビューには、1 つだけ定義があります。</span><span class="sxs-lookup"><span data-stu-id="c54a2-131">Typically, a view will have only one definition.</span></span> <span data-ttu-id="c54a2-132">ビューでのいくつかのプロパティを表示する 1 つの定義は、次の例では、 [System.Diagnostics.Process でしょうか。Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c54a2-132">In the following example, the view provides a single definition that displays several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="c54a2-133">リスト ビューには、プロパティの値またはスクリプト (この例では表示されません) の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-133">A list view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
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

```

<span data-ttu-id="c54a2-134">リスト ビューの定義を提供する、次の XML 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-134">The following XML elements can be used to provide definitions for a list view:</span></span>

- <span data-ttu-id="c54a2-135">[ListControl](./listcontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-135">The [ListControl](./listcontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="c54a2-136">[ListEntries](./listentries-element-for-listcontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-136">The [ListEntries](./listentries-element-for-listcontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="c54a2-137">ほとんどの場合、ビューは 1 つだけ定義になります。</span><span class="sxs-lookup"><span data-stu-id="c54a2-137">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="c54a2-138">この要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-138">This element is required.</span></span>

- <span data-ttu-id="c54a2-139">[ListEntry](./listentry-element-for-listcontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-139">The [ListEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="c54a2-140">少なくとも 1 つ[ListEntry](./listentry-element-for-listcontrol-format.md)が必要です。 ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-140">At least one [ListEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="c54a2-141">ほとんどの場合、ビューは 1 つだけ定義になります。</span><span class="sxs-lookup"><span data-stu-id="c54a2-141">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="c54a2-142">[EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-142">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="c54a2-143">この要素は省略可能と複数を定義する場合にのみ必要です[ListEntry](./listentry-element-for-listcontrol-format.md)さまざまなオブジェクトを表示する要素。</span><span class="sxs-lookup"><span data-stu-id="c54a2-143">This element is optional and is needed only when you define multiple [ListEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="c54a2-144">[ListItems](./listitems-element-for-listentry-for-listcontrol-format.md)要素は、プロパティと値を持つがリスト ビューの行に表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-144">The [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies the properties and scripts whose values are displayed in the rows of the list view.</span></span>

- <span data-ttu-id="c54a2-145">[ListItem](./listitems-element-for-listentry-for-listcontrol-format.md)要素は、プロパティまたはリスト ビューの行の値が表示されているスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-145">The [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies a property or script whose value is displayed in a row of the list view.</span></span> <span data-ttu-id="c54a2-146">リスト ビューには、少なくとも 1 つのプロパティまたはスクリプトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c54a2-146">A list view must specify at least one property or script.</span></span> <span data-ttu-id="c54a2-147">指定できる行の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-147">There is no maximum limit to the number of rows that can be specified.</span></span>

- <span data-ttu-id="c54a2-148">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素の値が行に表示プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-148">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="c54a2-149">プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-149">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="c54a2-150">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素の値が行に表示するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-150">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="c54a2-151">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-151">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="c54a2-152">[ラベル](./label-element-for-listitem-for-listcontrol-format.md)要素は、行のプロパティまたはスクリプトの値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-152">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element specifies the label that is displayed to the left of the property or script value in the row.</span></span> <span data-ttu-id="c54a2-153">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-153">This element is optional.</span></span> <span data-ttu-id="c54a2-154">ラベルが指定されていない場合、プロパティまたはスクリプトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-154">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="c54a2-155">完全な例を参照してください。[リスト ビュー (ラベル)](./list-view-labels.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-155">For a complete example, see [List View (Labels)](./list-view-labels.md).</span></span>

- <span data-ttu-id="c54a2-156">[ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)要素は、行を表示するのに必要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-156">The [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) element specifies a condition that must exist for the row to be displayed.</span></span> <span data-ttu-id="c54a2-157">リスト ビューに条件を追加する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-157">For more information about adding conditions to the list view, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span> <span data-ttu-id="c54a2-158">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-158">This element is optional.</span></span>

- <span data-ttu-id="c54a2-159">[FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md)要素は、プロパティ、またはスクリプトの値を表示するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-159">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a pattern that is used to display the value of the property or script.</span></span> <span data-ttu-id="c54a2-160">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-160">This element is optional.</span></span>

<span data-ttu-id="c54a2-161">単純なリスト ビューを定義する完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (Basic)](./list-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-161">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-list-view"></a><span data-ttu-id="c54a2-162">リスト ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-162">Defining the Objects That Use the List View</span></span>

<span data-ttu-id="c54a2-163">.NET オブジェクトを使用して、リスト ビューを定義する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="c54a2-163">There are two ways to define which .NET objects use the list view.</span></span> <span data-ttu-id="c54a2-164">使用することができます、 [ViewSelectedBy](./viewselectedby-element-format.md)するか、ビューのすべての定義を表示できるオブジェクトを定義する要素を使用できる、 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)によって表示されるオブジェクトを定義する要素、ビューの定義を特定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-164">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="c54a2-165">ほとんどの場合、ビューでは 1 つだけ定義は、オブジェクトは通常で定義されるため、 [ViewSelectedBy](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c54a2-165">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="c54a2-166">次の例は、リスト ビューを使用して表示されるオブジェクトを定義する方法を示します、 [ViewSelectedBy](./viewselectedby-element-format.md)と[TypeName](./typename-element-for-viewselectedby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c54a2-166">The following example shows how to define the objects that are displayed by the list view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="c54a2-167">数に制限はありません[TypeName](./typename-element-for-viewselectedby-format.md)要素を指定できますが、およびその順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-167">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="c54a2-168">次の XML 要素を使用して、リスト ビューで使用されるオブジェクトを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-168">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="c54a2-169">[ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-169">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="c54a2-170">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-170">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="c54a2-171">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-171">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="c54a2-172">少なくとも 1 つの型またはビューの設定の選択範囲を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-172">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="c54a2-173">完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (Basic)](./list-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-173">For an example of a complete formatting file, see [List View (Basic)](./list-view-basic.md).</span></span>

<span data-ttu-id="c54a2-174">次の例では、 [ViewSelectedBy](./viewselectedby-element-format.md)と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c54a2-174">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="c54a2-175">関連する一連の同じオブジェクトのリスト ビューを定義する場合など、複数のビューおよびテーブル ビューを使用して表示されるオブジェクトがある選択範囲のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-175">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="c54a2-176">選択範囲のセットを作成する方法の詳細については、次を参照してください。[選択範囲のセットを定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-176">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="c54a2-177">次の XML 要素を使用して、リスト ビューで使用されるオブジェクトを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-177">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="c54a2-178">[ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-178">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="c54a2-179">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、一連のビューで表示できるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-179">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="c54a2-180">少なくとも 1 つの選択範囲のセットまたはビューの種類を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-180">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="c54a2-181">次の例は、特定の定義を使用してリスト ビューで表示されるオブジェクトを定義する方法を示します、 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c54a2-181">The following example shows how to define the objects displayed by a specific definition of the list view using the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element.</span></span> <span data-ttu-id="c54a2-182">この要素を使用して、オブジェクト、オブジェクトの選択範囲のセットまたは定義を使用する場合を指定する選択条件の .NET 型名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-182">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="c54a2-183">選択条件を作成する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-183">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

<span data-ttu-id="c54a2-184">リスト ビューの特定の定義で使用されるオブジェクトを指定する、次の XML 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-184">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="c54a2-185">[EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-185">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="c54a2-186">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)要素を定義して表示されている .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-186">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="c54a2-187">この要素を使用する場合は、完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-187">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="c54a2-188">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="c54a2-189">[SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-189">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="c54a2-190">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-190">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="c54a2-191">[SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義を使用するのに必要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-191">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="c54a2-192">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-192">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="c54a2-193">選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-193">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-list-view"></a><span data-ttu-id="c54a2-194">リスト ビューでオブジェクトのグループを表示します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-194">Displaying Groups of Objects in a List View</span></span>

<span data-ttu-id="c54a2-195">グループに、リスト ビューで表示されているオブジェクトを分離することができます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-195">You can separate the objects that are displayed by the list view into groups.</span></span> <span data-ttu-id="c54a2-196">限りませんグループを定義するだけで、特定のプロパティまたはスクリプトの値が変更されるたびに、その Windows PowerShell は新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-196">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="c54a2-197">次の例で新しいグループが開始されるたびの値、 [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの変更。</span><span class="sxs-lookup"><span data-stu-id="c54a2-197">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="c54a2-198">次の XML 要素は、グループの開始時に定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-198">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="c54a2-199">[GroupBy](./groupby-element-for-view-format.md)プロパティまたは新しいグループを開始し、グループの表示方法を定義するスクリプト要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-199">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="c54a2-200">[PropertyName](./propertyname-element-for-groupby-format.md)要素は、その値が変更されるたびに新しいグループを開始するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-200">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="c54a2-201">プロパティまたはグループを開始するスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-201">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="c54a2-202">[ScriptBlock](./scriptblock-element-for-groupby-format.md)要素は、その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-202">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="c54a2-203">スクリプトまたはグループを開始するプロパティを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-203">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="c54a2-204">[ラベル](./label-element-for-groupby-format.md)要素は、各グループの先頭に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-204">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="c54a2-205">この要素で指定されたテキスト、だけでなく Windows PowerShell には、新しいグループがトリガーされ、ラベルの前後に空白行を追加する値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-205">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="c54a2-206">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-206">This element is optional.</span></span>

- <span data-ttu-id="c54a2-207">[カスタム コントロール](./customcontrol-element-for-groupby-format.md)要素は、データを表示するために使用するコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-207">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="c54a2-208">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-208">This element is optional.</span></span>

- <span data-ttu-id="c54a2-209">[CustomControlName](./customcontrolname-element-for-groupby-format.md)要素は、一般的なを指定します。 または、データを表示するために使用するコントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-209">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="c54a2-210">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c54a2-210">This element is optional.</span></span>

<span data-ttu-id="c54a2-211">グループを定義する完全な書式設定ファイルの例は、次を参照してください。[リスト ビュー (GroupBy)](./list-view-groupby.md)します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-211">For an example of a complete formatting file that defines groups, see [List View (GroupBy)](./list-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="c54a2-212">書式指定文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-212">Using Format Strings</span></span>

<span data-ttu-id="c54a2-213">さらに、データの表示方法を定義するビューには、書式設定文字列を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-213">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="c54a2-214">次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c54a2-214">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

<span data-ttu-id="c54a2-215">次の XML 要素を使用して、書式パターンを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-215">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="c54a2-216">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-216">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="c54a2-217">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素が値を持つが、ビューによって表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-217">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="c54a2-218">プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-218">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="c54a2-219">[FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md)要素は、ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-219">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

- <span data-ttu-id="c54a2-220">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-220">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="c54a2-221">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-221">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="c54a2-222">次の例では、`ToString`スクリプトの値の書式設定メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-222">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="c54a2-223">スクリプトでは、オブジェクトのすべてのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-223">Scripts can call any method of an object.</span></span> <span data-ttu-id="c54a2-224">そのため、オブジェクトが、メソッドがなど`ToString`、書式設定パラメーターを持つ、スクリプトは、スクリプトの出力値の書式を指定するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c54a2-224">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="c54a2-225">次の XML 要素を呼び出すことができます、`ToString`メソッド。</span><span class="sxs-lookup"><span data-stu-id="c54a2-225">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="c54a2-226">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-226">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="c54a2-227">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (表示されない) 要素をビューで表示される値を持つスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c54a2-227">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="c54a2-228">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c54a2-228">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="c54a2-229">参照</span><span class="sxs-lookup"><span data-stu-id="c54a2-229">See Also</span></span>

[<span data-ttu-id="c54a2-230">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c54a2-230">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/writing-a-windows-powershell-cmdlet.md)
