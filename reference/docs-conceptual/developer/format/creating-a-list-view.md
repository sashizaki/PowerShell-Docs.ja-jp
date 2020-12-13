---
ms.date: 09/13/2016
ms.topic: reference
title: リスト ビューを作成する
description: リスト ビューを作成する
ms.openlocfilehash: c34c4fddc27d4fd016fba37fc465924d693756a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655638"
---
# <a name="creating-a-list-view"></a><span data-ttu-id="80f92-103">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="80f92-103">Creating a List View</span></span>

<span data-ttu-id="80f92-104">リストビューでは、1つの列にデータが順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="80f92-104">A list view displays data in a single column (in sequential order).</span></span> <span data-ttu-id="80f92-105">一覧に表示されるデータは、.NET プロパティの値、またはスクリプトの値にすることができます。</span><span class="sxs-lookup"><span data-stu-id="80f92-105">The data displayed in the list can be the value of a .NET property or the value of a script.</span></span>

## <a name="a-list-view-display"></a><span data-ttu-id="80f92-106">リストビューの表示</span><span class="sxs-lookup"><span data-stu-id="80f92-106">A List View Display</span></span>

<span data-ttu-id="80f92-107">次の出力は、Windows PowerShell が Servicecontroller のプロパティをどのように表示するかを示しています。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) [Get Service](/powershell/module/microsoft.powershell.management/get-service) コマンドレットによって返される Fullname オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80f92-107">The following output shows how Windows PowerShell displays the properties of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects that are returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="80f92-108">この例では、3つのオブジェクトが返されました。各オブジェクトは、前のオブジェクトから空白行に区切られています。</span><span class="sxs-lookup"><span data-stu-id="80f92-108">In this example, three objects were returned, with each object separated from the preceding object by a blank line.</span></span>

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

## <a name="defining-the-list-view"></a><span data-ttu-id="80f92-109">リストビューの定義</span><span class="sxs-lookup"><span data-stu-id="80f92-109">Defining the List View</span></span>

<span data-ttu-id="80f92-110">次の XML は、Servicecontroller のいくつかのプロパティを表示するためのリストビュースキーマを示して [います。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80f92-110">The following XML shows the list view schema for displaying several properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="80f92-111">リストビューに表示する各プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f92-111">You must specify each property that you want displayed in the list view.</span></span>

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

<span data-ttu-id="80f92-112">リストビューを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="80f92-112">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="80f92-113">[ビュー](./view-element-format.md)要素は、リストビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="80f92-113">The [View](./view-element-format.md) element is the parent element of the list view.</span></span> <span data-ttu-id="80f92-114">(これは、テーブル、ワイド、およびカスタムコントロールビューの親要素と同じです)。</span><span class="sxs-lookup"><span data-stu-id="80f92-114">(This is the same parent element for the table, wide, and custom control views.)</span></span>

- <span data-ttu-id="80f92-115">[Name](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="80f92-116">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="80f92-116">This element is required for all views.</span></span>

- <span data-ttu-id="80f92-117">[Viewselectedby](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="80f92-118">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="80f92-118">This element is required.</span></span>

- <span data-ttu-id="80f92-119">[GroupBy](./groupby-element-for-view-format.md)要素は、オブジェクトの新しいグループが表示されるタイミングを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="80f92-120">特定のプロパティまたはスクリプトの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="80f92-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="80f92-121">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-121">This element is optional.</span></span>

- <span data-ttu-id="80f92-122">[Controls](./controls-element-for-view-format.md)要素は、リストビューによって定義されるカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-122">The [Controls](./controls-element-for-view-format.md) element defines the custom controls that are defined by the list view.</span></span> <span data-ttu-id="80f92-123">コントロールを使用すると、データの表示方法をさらに指定することができます。</span><span class="sxs-lookup"><span data-stu-id="80f92-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="80f92-124">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-124">This element is optional.</span></span> <span data-ttu-id="80f92-125">ビューでは、独自のカスタムコントロールを定義することも、書式設定ファイルの任意のビューで使用できるコモンコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="80f92-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="80f92-126">カスタムコントロールの詳細については、「 [カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="80f92-127">[ListControl](./listcontrol-element-format.md)要素は、ビューに表示される内容と書式設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-127">The [ListControl](./listcontrol-element-format.md) element defines what is displayed in the view and how it is formatted.</span></span> <span data-ttu-id="80f92-128">他のすべてのビューと同様に、リストビューでは、オブジェクトのプロパティまたはスクリプトによって生成される値の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-128">Similar to all other views, a list view can display the values of object properties or values generated by script.</span></span>

<span data-ttu-id="80f92-129">単純なリストビューを定義する完全な書式設定ファイルの例については、「 [リストビュー (基本)](./list-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-129">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-list-view"></a><span data-ttu-id="80f92-130">リストビューの定義を指定する</span><span class="sxs-lookup"><span data-stu-id="80f92-130">Providing Definitions for Your List View</span></span>

<span data-ttu-id="80f92-131">リストビューでは、 [ListControl](./listcontrol-element-format.md) 要素の子要素を使用して1つまたは複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-131">List views can provide one or more definitions by using the child elements of the [ListControl](./listcontrol-element-format.md) element.</span></span> <span data-ttu-id="80f92-132">通常、ビューの定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="80f92-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="80f92-133">次の例では、ビューには、システムの複数のプロパティを表示する1つの定義が用意されています。 [Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80f92-133">In the following example, the view provides a single definition that displays several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="80f92-134">リストビューでは、プロパティの値またはスクリプトの値を表示できます (例には示されていません)。</span><span class="sxs-lookup"><span data-stu-id="80f92-134">A list view can display the value of a property or the value of a script (not shown in the example).</span></span>

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

<span data-ttu-id="80f92-135">次の XML 要素を使用して、リストビューの定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-135">The following XML elements can be used to provide definitions for a list view:</span></span>

- <span data-ttu-id="80f92-136">[ListControl](./listcontrol-element-format.md)要素とその子要素は、ビューに表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-136">The [ListControl](./listcontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="80f92-137">[Listentries](./listentries-element-for-listcontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="80f92-137">The [ListEntries](./listentries-element-for-listcontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="80f92-138">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="80f92-138">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="80f92-139">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="80f92-139">This element is required.</span></span>

- <span data-ttu-id="80f92-140">[ListEntry](./listentry-element-for-listcontrol-format.md)要素は、ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="80f92-140">The [ListEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="80f92-141">少なくとも1つの [ListEntry](./listentry-element-for-listcontrol-format.md) が必要です。ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-141">At least one [ListEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="80f92-142">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="80f92-142">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="80f92-143">[Entryselectedby](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-143">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="80f92-144">この要素は省略可能であり、異なるオブジェクトを表示する複数の [ListEntry](./listentry-element-for-listcontrol-format.md) 要素を定義する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="80f92-144">This element is optional and is needed only when you define multiple [ListEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="80f92-145">[ListItems](./listitems-element-for-listentry-for-listcontrol-format.md)要素は、リストビューの行に値が表示されるプロパティとスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-145">The [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies the properties and scripts whose values are displayed in the rows of the list view.</span></span>

- <span data-ttu-id="80f92-146">[ListItem](./listitems-element-for-listentry-for-listcontrol-format.md)要素は、リストビューの行に表示される値を持つプロパティまたはスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-146">The [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies a property or script whose value is displayed in a row of the list view.</span></span> <span data-ttu-id="80f92-147">リストビューでは、少なくとも1つのプロパティまたはスクリプトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f92-147">A list view must specify at least one property or script.</span></span> <span data-ttu-id="80f92-148">指定できる行の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-148">There is no maximum limit to the number of rows that can be specified.</span></span>

- <span data-ttu-id="80f92-149">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素は、値が行に表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-149">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="80f92-150">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="80f92-150">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="80f92-151">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素は、値が行に表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-151">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="80f92-152">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="80f92-152">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="80f92-153">[Label](./label-element-for-listitem-for-listcontrol-format.md)要素は、行のプロパティまたはスクリプト値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-153">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element specifies the label that is displayed to the left of the property or script value in the row.</span></span> <span data-ttu-id="80f92-154">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-154">This element is optional.</span></span> <span data-ttu-id="80f92-155">ラベルが指定されていない場合は、プロパティまたはスクリプトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80f92-155">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="80f92-156">完全な例については、「 [リストビュー (ラベル)](./list-view-labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-156">For a complete example, see [List View (Labels)](./list-view-labels.md).</span></span>

- <span data-ttu-id="80f92-157">[Itemselectioncondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)要素は、表示される行に対して存在する必要がある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-157">The [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) element specifies a condition that must exist for the row to be displayed.</span></span> <span data-ttu-id="80f92-158">リストビューに条件を追加する方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-158">For more information about adding conditions to the list view, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span> <span data-ttu-id="80f92-159">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-159">This element is optional.</span></span>

- <span data-ttu-id="80f92-160">[FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値を表示するために使用されるパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-160">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a pattern that is used to display the value of the property or script.</span></span> <span data-ttu-id="80f92-161">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-161">This element is optional.</span></span>

<span data-ttu-id="80f92-162">単純なリストビューを定義する完全な書式設定ファイルの例については、「 [リストビュー (基本)](./list-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-162">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-list-view"></a><span data-ttu-id="80f92-163">リストビューを使用するオブジェクトの定義</span><span class="sxs-lookup"><span data-stu-id="80f92-163">Defining the Objects That Use the List View</span></span>

<span data-ttu-id="80f92-164">リストビューを使用する .NET オブジェクトを定義するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="80f92-164">There are two ways to define which .NET objects use the list view.</span></span> <span data-ttu-id="80f92-165">[Viewselectedby](./viewselectedby-element-format.md)要素を使用すると、ビューのすべての定義で表示できるオブジェクトを定義できます。また、 [entryselectedby](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素を使用して、ビューの特定の定義によって表示されるオブジェクトを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="80f92-165">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="80f92-166">ほとんどの場合、ビューには定義が1つしかないため、オブジェクトは通常、 [Viewselectedby](./viewselectedby-element-format.md) 要素によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="80f92-166">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="80f92-167">次の例は、 [Viewselectedby](./viewselectedby-element-format.md) および [TypeName](./typename-element-for-viewselectedby-format.md) 要素を使用してリストビューに表示されるオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="80f92-167">The following example shows how to define the objects that are displayed by the list view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="80f92-168">指定できる [TypeName](./typename-element-for-viewselectedby-format.md) 要素の数に制限はありません。これらの要素の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-168">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="80f92-169">次の XML 要素を使用して、リストビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-169">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="80f92-170">[Viewselectedby](./viewselectedby-element-format.md)要素は、リストビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-170">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="80f92-171">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .net オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-171">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="80f92-172">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="80f92-172">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="80f92-173">ビューには少なくとも1つの種類または選択セットを指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-173">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="80f92-174">完全な書式設定ファイルの例については、「 [リストビュー (基本)](./list-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-174">For an example of a complete formatting file, see [List View (Basic)](./list-view-basic.md).</span></span>

<span data-ttu-id="80f92-175">次の例では、 [Viewselectedby](./viewselectedby-element-format.md) 要素と [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="80f92-175">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="80f92-176">複数のビューを使用して表示される関連オブジェクトのセットがある場合、たとえば、同じオブジェクトのリストビューやテーブルビューを定義するときに、選択セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="80f92-176">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="80f92-177">選択セットを作成する方法の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-177">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="80f92-178">次の XML 要素を使用して、リストビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-178">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="80f92-179">[Viewselectedby](./viewselectedby-element-format.md)要素は、リストビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-179">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="80f92-180">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、ビューで表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-180">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="80f92-181">ビューには少なくとも1つの選択セットまたは型を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-181">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="80f92-182">次の例では、 [Entryselectedby](./entryselectedby-element-for-listentry-for-listcontrol-format.md) 要素を使用して、リストビューの特定の定義によって表示されるオブジェクトを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="80f92-182">The following example shows how to define the objects displayed by a specific definition of the list view using the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element.</span></span> <span data-ttu-id="80f92-183">この要素を使用して、オブジェクトの .NET 型名、選択したオブジェクトのセット、または定義を使用するタイミングを指定する選択条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-183">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="80f92-184">選択条件を作成する方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-184">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

<span data-ttu-id="80f92-185">次の XML 要素を使用して、リストビューの特定の定義によって使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-185">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="80f92-186">[Entryselectedby](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素は、定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-186">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="80f92-187">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)要素は、定義によって表示される .net オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-187">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="80f92-188">この要素を使用する場合は、完全修飾された .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="80f92-188">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="80f92-189">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-189">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="80f92-190">[SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)要素 (表示されません) は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-190">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="80f92-191">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-191">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="80f92-192">[Selectioncondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)要素 (表示されません) は、この定義を使用するために存在する必要がある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-192">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="80f92-193">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="80f92-193">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="80f92-194">選択条件の定義の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-194">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-list-view"></a><span data-ttu-id="80f92-195">リストビューでのオブジェクトのグループの表示</span><span class="sxs-lookup"><span data-stu-id="80f92-195">Displaying Groups of Objects in a List View</span></span>

<span data-ttu-id="80f92-196">リストビューによって表示されるオブジェクトをグループに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="80f92-196">You can separate the objects that are displayed by the list view into groups.</span></span> <span data-ttu-id="80f92-197">これは、グループを定義することではなく、特定のプロパティまたはスクリプトの値が変更されるたびに、Windows PowerShell によって新しいグループが開始されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="80f92-197">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="80f92-198">次の例では、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) プロパティの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="80f92-198">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="80f92-199">グループがいつ開始されるかを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="80f92-199">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="80f92-200">[GroupBy](./groupby-element-for-view-format.md)要素は、新しいグループを開始するプロパティまたはスクリプトを定義し、グループの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-200">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="80f92-201">[PropertyName](./propertyname-element-for-groupby-format.md)要素は、値が変更されるたびに新しいグループを開始するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-201">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="80f92-202">グループを開始するには、プロパティまたはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="80f92-202">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="80f92-203">[ScriptBlock](./scriptblock-element-for-groupby-format.md)要素は、値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-203">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="80f92-204">グループを開始するには、スクリプトまたはプロパティを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="80f92-204">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="80f92-205">[Label](./label-element-for-groupby-format.md)要素は、各グループの先頭に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-205">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="80f92-206">Windows PowerShell は、この要素で指定されたテキストに加えて、新しいグループをトリガーした値を表示し、ラベルの前後に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="80f92-206">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="80f92-207">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-207">This element is optional.</span></span>

- <span data-ttu-id="80f92-208">[CustomControl](./customcontrol-element-for-groupby-format.md)要素は、データの表示に使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="80f92-208">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="80f92-209">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-209">This element is optional.</span></span>

- <span data-ttu-id="80f92-210">[CustomControlName](./customcontrolname-element-for-groupby-format.md)要素は、データの表示に使用されるコモンコントロールまたはビューコントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-210">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="80f92-211">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80f92-211">This element is optional.</span></span>

<span data-ttu-id="80f92-212">グループを定義する完全な書式設定ファイルの例については、「 [リストビュー (GroupBy)](./list-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f92-212">For an example of a complete formatting file that defines groups, see [List View (GroupBy)](./list-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="80f92-213">書式指定文字列の使用</span><span class="sxs-lookup"><span data-stu-id="80f92-213">Using Format Strings</span></span>

<span data-ttu-id="80f92-214">書式設定文字列をビューに追加して、データの表示方法をさらに定義できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-214">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="80f92-215">次の例は、プロパティの値の書式設定文字列を定義する方法を示して `StartTime` います。</span><span class="sxs-lookup"><span data-stu-id="80f92-215">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

<span data-ttu-id="80f92-216">次の XML 要素を使用して、書式パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-216">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="80f92-217">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-217">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="80f92-218">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素は、ビューによって表示される値を持つプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-218">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="80f92-219">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="80f92-219">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="80f92-220">[FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-220">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

- <span data-ttu-id="80f92-221">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素 (表示されません) は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-221">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="80f92-222">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="80f92-222">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="80f92-223">次の例では、 `ToString` スクリプトの値の書式を設定するためにメソッドが呼び出されています。</span><span class="sxs-lookup"><span data-stu-id="80f92-223">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="80f92-224">スクリプトは、オブジェクトの任意のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="80f92-224">Scripts can call any method of an object.</span></span> <span data-ttu-id="80f92-225">したがって、オブジェクトに、書式設定パラメーターを持つなどのメソッドがある場合、 `ToString` スクリプトはそのメソッドを呼び出してスクリプトの出力値を書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="80f92-225">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="80f92-226">次の XML 要素を使用して、メソッドを呼び出すことができ `ToString` ます。</span><span class="sxs-lookup"><span data-stu-id="80f92-226">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="80f92-227">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md)要素は、ビューによって表示されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-227">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="80f92-228">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素 (表示されません) は、ビューによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f92-228">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="80f92-229">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="80f92-229">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="80f92-230">参照</span><span class="sxs-lookup"><span data-stu-id="80f92-230">See Also</span></span>

[<span data-ttu-id="80f92-231">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="80f92-231">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/writing-a-windows-powershell-cmdlet.md)
