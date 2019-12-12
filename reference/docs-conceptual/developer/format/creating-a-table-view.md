---
title: テーブルビューを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f405afb-70b5-4fe0-9986-bc07401d93fd
caps.latest.revision: 23
ms.openlocfilehash: 862f942facafff6cea66c4f8f1040772c6a62ec3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363411"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="a9aa3-102">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="a9aa3-102">Creating a Table View</span></span>

<span data-ttu-id="a9aa3-103">テーブルビューでは、1つまたは複数の列にデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-103">A table view displays data in one or more columns.</span></span> <span data-ttu-id="a9aa3-104">テーブルの各行は .NET オブジェクトを表し、テーブルの各列はオブジェクトのプロパティまたはスクリプト値を表します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-104">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="a9aa3-105">オブジェクトのすべてのプロパティ、またはオブジェクトのプロパティのサブセットを表示するテーブルビューを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-105">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="a9aa3-106">テーブルビューの表示</span><span class="sxs-lookup"><span data-stu-id="a9aa3-106">A Table View Display</span></span>

<span data-ttu-id="a9aa3-107">次の例では、Servicecontroller コマンドレット[Get-Service](/powershell/module/microsoft.powershell.management/get-service)によって返される[System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトが Windows PowerShell によってどのように表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-107">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="a9aa3-108">このオブジェクトの場合、Windows PowerShell では、`Status` プロパティ、`Name` プロパティ (このプロパティは `ServiceName` プロパティのエイリアスプロパティ)、および `DisplayName` プロパティを表示するテーブルビューが定義されています。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-108">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="a9aa3-109">テーブルの各行は、コマンドレットによって返されるオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-109">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="a9aa3-110">テーブルビューの定義</span><span class="sxs-lookup"><span data-stu-id="a9aa3-110">Defining the Table View</span></span>

<span data-ttu-id="a9aa3-111">次の XML は、Servicecontroller を表示するためのテーブルビュースキーマを示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-111">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="a9aa3-112">テーブルビューに表示する各プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-112">You must specify each property that you want displayed in the table view.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>8</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>18</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>38</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

<span data-ttu-id="a9aa3-113">リストビューを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-113">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="a9aa3-114">[View](./view-element-format.md)要素は、テーブルビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-114">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="a9aa3-115">(これは、リスト、ワイド、およびカスタムコントロールビューの親要素と同じです)。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-115">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="a9aa3-116">[Name](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-116">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="a9aa3-117">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-117">This element is required for all views.</span></span>

- <span data-ttu-id="a9aa3-118">[Viewselectedby](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-118">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="a9aa3-119">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-119">This element is required.</span></span>

- <span data-ttu-id="a9aa3-120">[GroupBy](./groupby-element-for-view-format.md)要素 (この例では示されていません) は、オブジェクトの新しいグループが表示されるタイミングを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-120">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="a9aa3-121">特定のプロパティまたはスクリプトの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-121">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="a9aa3-122">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-122">This element is optional.</span></span>

- <span data-ttu-id="a9aa3-123">[Controls](./controls-element-for-view-format.md)要素 (この例では示されていません) は、テーブルビューで定義されるカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-123">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="a9aa3-124">コントロールを使用すると、データの表示方法をさらに指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-124">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="a9aa3-125">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-125">This element is optional.</span></span> <span data-ttu-id="a9aa3-126">ビューでは、独自のカスタムコントロールを定義することも、書式設定ファイルの任意のビューで使用できるコモンコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-126">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="a9aa3-127">カスタムコントロールの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-127">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="a9aa3-128">[Hidetableheaders](./hidetableheaders-element-format.md)要素 (この例では示されていません) は、テーブルの先頭にラベルが表示されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-128">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="a9aa3-129">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-129">This element is optional.</span></span>

- <span data-ttu-id="a9aa3-130">テーブルのヘッダーと行の情報を定義する[Tablecontrol](./tablecontrol-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-130">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="a9aa3-131">他のすべてのビューと同様に、テーブルビューでは、オブジェクトのプロパティの値や、スクリプトによって生成される値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-131">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="a9aa3-132">列ヘッダーの定義</span><span class="sxs-lookup"><span data-stu-id="a9aa3-132">Defining Column Headers</span></span>

1. <span data-ttu-id="a9aa3-133">[Tableheaders](./tableheaders-element-format.md)要素とその子要素は、テーブルの上部に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-133">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="a9aa3-134">[TableColumnHeader](./tablecolumnheader-element-format.md)要素は、テーブルの列の上部に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-134">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="a9aa3-135">これらの要素は、ヘッダーを表示する順序で指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-135">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="a9aa3-136">使用できる要素の数に制限はありませんが、テーブルビュー内の[TableColumnHeader](./tablecolumnheader-element-format.md)要素の数は、使用する[TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)要素の数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-136">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="a9aa3-137">[Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-137">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="a9aa3-138">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-138">This element is optional.</span></span>

4. <span data-ttu-id="a9aa3-139">[Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、列の幅 (文字数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-139">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="a9aa3-140">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-140">This element is optional.</span></span>

5. <span data-ttu-id="a9aa3-141">[Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、ラベルの表示方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-141">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="a9aa3-142">ラベルは左、右、または中央に配置できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-142">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="a9aa3-143">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-143">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="a9aa3-144">テーブル行の定義</span><span class="sxs-lookup"><span data-stu-id="a9aa3-144">Defining the Table Rows</span></span>

<span data-ttu-id="a9aa3-145">テーブルビューでは、 [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)要素の子要素を使用して、テーブルの行に表示されるデータを指定する1つ以上の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-145">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="a9aa3-146">テーブルの行に対して複数の定義を指定できますが、使用されている行の定義に関係なく、行のヘッダーは同じままです。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-146">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="a9aa3-147">通常、テーブルの定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-147">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="a9aa3-148">次の例では、ビューには、システムの複数のプロパティの値を表示する1つの定義が用意されています。 [Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-148">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="a9aa3-149">テーブルビューでは、プロパティの値やスクリプトの値 (例では示されていません) を行に表示できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-149">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

```xml
<TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>

```

<span data-ttu-id="a9aa3-150">次の XML 要素を使用して、行の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-150">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="a9aa3-151">[TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)要素とその子要素は、テーブルの行に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-151">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="a9aa3-152">[TableRowEntry](./listentry-element-for-listcontrol-format.md)要素は、行の定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-152">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="a9aa3-153">少なくとも1つの[TableRowEntry](./listentry-element-for-listcontrol-format.md)が必要です。ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-153">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="a9aa3-154">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-154">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="a9aa3-155">[Entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-155">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="a9aa3-156">この要素は省略可能であり、異なるオブジェクトを表示する複数の[TableRowEntry](./listentry-element-for-listcontrol-format.md)要素を定義する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-156">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="a9aa3-157">[Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)要素は、列幅を超えるテキストを次の行に表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-157">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="a9aa3-158">既定では、列幅を超えるテキストは切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-158">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="a9aa3-159">[TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)要素は、値が行に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-159">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="a9aa3-160">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、値が行の列に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-160">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="a9aa3-161">行の各列には[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-161">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="a9aa3-162">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-162">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="a9aa3-163">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-163">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="a9aa3-164">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-164">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="a9aa3-165">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-165">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="a9aa3-166">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-166">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="a9aa3-167">[FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-167">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="a9aa3-168">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-168">This element is optional.</span></span>

- <span data-ttu-id="a9aa3-169">[Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、プロパティまたはスクリプトの値の表示方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-169">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="a9aa3-170">値は、左、右、または中央揃えに配置できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-170">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="a9aa3-171">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-171">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="a9aa3-172">テーブルビューを使用するオブジェクトの定義</span><span class="sxs-lookup"><span data-stu-id="a9aa3-172">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="a9aa3-173">テーブルビューを使用する .NET オブジェクトを定義するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-173">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="a9aa3-174">[Viewselectedby](./viewselectedby-element-format.md)要素を使用すると、ビューのすべての定義で表示できるオブジェクトを定義できます。また、 [entryselectedby](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素を使用して、ビューの特定の定義によって表示されるオブジェクトを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-174">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="a9aa3-175">ほとんどの場合、ビューには定義が1つしかないため、オブジェクトは通常、 [Viewselectedby](./viewselectedby-element-format.md)要素によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-175">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="a9aa3-176">次の例は、 [Viewselectedby](./viewselectedby-element-format.md)および[TypeName](./typename-element-for-viewselectedby-format.md)要素を使用してテーブルビューに表示されるオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-176">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="a9aa3-177">指定できる[TypeName](./typename-element-for-viewselectedby-format.md)要素の数に制限はありません。これらの要素の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-177">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="a9aa3-178">次の XML 要素を使用して、テーブルビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-178">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="a9aa3-179">[Viewselectedby](./viewselectedby-element-format.md)要素は、リストビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-179">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="a9aa3-180">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .net オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-180">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="a9aa3-181">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-181">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="a9aa3-182">ビューには少なくとも1つの種類または選択セットを指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-182">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="a9aa3-183">次の例では、 [Viewselectedby](./viewselectedby-element-format.md)要素と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-183">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="a9aa3-184">複数のビューを使用して表示される関連オブジェクトのセットがある場合、たとえば、同じオブジェクトのリストビューやテーブルビューを定義するときに、選択セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-184">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="a9aa3-185">選択セットを作成する方法の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-185">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="a9aa3-186">次の XML 要素を使用して、リストビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-186">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="a9aa3-187">[Viewselectedby](./viewselectedby-element-format.md)要素は、リストビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-187">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="a9aa3-188">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、ビューで表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-188">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="a9aa3-189">ビューには少なくとも1つの選択セットまたは型を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-189">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="a9aa3-190">次の例では、 [Entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素を使用して、テーブルビューの特定の定義によって表示されるオブジェクトを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-190">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="a9aa3-191">この要素を使用して、オブジェクトの .NET 型名、選択したオブジェクトのセット、または定義を使用するタイミングを指定する選択条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-191">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="a9aa3-192">選択条件を作成する方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-192">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a9aa3-193">テーブルビューの複数の定義を作成する場合は、異なる列ヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-193">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="a9aa3-194">表示するオブジェクトなど、テーブルの行に表示されるもののみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-194">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="a9aa3-195">次の XML 要素を使用して、リストビューの特定の定義によって使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-195">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="a9aa3-196">[Entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素は、定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-196">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="a9aa3-197">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)要素は、定義によって表示される .net オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-197">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="a9aa3-198">この要素を使用する場合は、完全修飾された .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-198">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="a9aa3-199">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-199">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="a9aa3-200">[SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)要素 (表示されません) は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-200">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="a9aa3-201">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-201">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="a9aa3-202">[Selectioncondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)要素 (表示されません) は、この定義を使用するために存在する必要がある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-202">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="a9aa3-203">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-203">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="a9aa3-204">選択条件の定義の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-204">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="a9aa3-205">書式指定文字列の使用</span><span class="sxs-lookup"><span data-stu-id="a9aa3-205">Using Format Strings</span></span>

<span data-ttu-id="a9aa3-206">書式設定文字列をビューに追加して、データの表示方法をさらに定義できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-206">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="a9aa3-207">次の例は、`StartTime` プロパティの値の書式設定文字列を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-207">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="a9aa3-208">次の XML 要素を使用して、書式パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-208">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="a9aa3-209">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、値が行の列に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-209">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="a9aa3-210">行の各列には[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-210">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="a9aa3-211">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-211">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="a9aa3-212">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-212">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="a9aa3-213">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-213">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="a9aa3-214">[FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-214">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="a9aa3-215">次の例では、スクリプトの値の書式を設定するために、`ToString` メソッドが呼び出されています。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-215">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="a9aa3-216">スクリプトは、オブジェクトの任意のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-216">Scripts can call any method of an object.</span></span> <span data-ttu-id="a9aa3-217">したがって、オブジェクトに、書式設定パラメーターを持つメソッド (`ToString`など) がある場合、スクリプトはそのメソッドを呼び出してスクリプトの出力値を書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-217">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="a9aa3-218">次の XML 要素を使用して、`ToString` メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-218">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="a9aa3-219">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、値が行の列に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-219">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="a9aa3-220">行の各列には[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-220">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="a9aa3-221">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-221">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="a9aa3-222">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-222">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="a9aa3-223">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9aa3-223">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9aa3-224">参照</span><span class="sxs-lookup"><span data-stu-id="a9aa3-224">See Also</span></span>

[<span data-ttu-id="a9aa3-225">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="a9aa3-225">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
