---
ms.date: 09/13/2016
ms.topic: reference
title: テーブル ビューを作成する
description: テーブル ビューを作成する
ms.openlocfilehash: 035d42f7968a9e8babec692a7a5873e24b36cd97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660289"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="3ae29-103">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="3ae29-103">Creating a Table View</span></span>

<span data-ttu-id="3ae29-104">テーブルビューでは、1つまたは複数の列にデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-104">A table view displays data in one or more columns.</span></span> <span data-ttu-id="3ae29-105">テーブルの各行は .NET オブジェクトを表し、テーブルの各列はオブジェクトのプロパティまたはスクリプト値を表します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-105">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="3ae29-106">オブジェクトのすべてのプロパティ、またはオブジェクトのプロパティのサブセットを表示するテーブルビューを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-106">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="3ae29-107">テーブルビューの表示</span><span class="sxs-lookup"><span data-stu-id="3ae29-107">A Table View Display</span></span>

<span data-ttu-id="3ae29-108">次の例で[は、Servicecontroller コマンドレット](/powershell/module/microsoft.powershell.management/get-service)によって返される[](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトが Windows PowerShell によってどのように表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-108">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="3ae29-109">このオブジェクトの場合、Windows PowerShell では、プロパティ、プロパティ `Status` (このプロパティ `Name` はプロパティのエイリアスプロパティ)、およびプロパティを表示するテーブルビューが定義されてい `ServiceName` `DisplayName` ます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-109">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="3ae29-110">テーブルの各行は、コマンドレットによって返されるオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-110">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="3ae29-111">テーブルビューの定義</span><span class="sxs-lookup"><span data-stu-id="3ae29-111">Defining the Table View</span></span>

<span data-ttu-id="3ae29-112">次の XML は、Servicecontroller を表示するためのテーブルビュースキーマを示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3ae29-112">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="3ae29-113">テーブルビューに表示する各プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae29-113">You must specify each property that you want displayed in the table view.</span></span>

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

<span data-ttu-id="3ae29-114">リストビューを定義するには、次の XML 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-114">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="3ae29-115">[View](./view-element-format.md)要素は、テーブルビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-115">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="3ae29-116">(これは、リスト、ワイド、およびカスタムコントロールビューの親要素と同じです)。</span><span class="sxs-lookup"><span data-stu-id="3ae29-116">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="3ae29-117">[Name](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-117">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="3ae29-118">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-118">This element is required for all views.</span></span>

- <span data-ttu-id="3ae29-119">[Viewselectedby](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-119">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="3ae29-120">この要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-120">This element is required.</span></span>

- <span data-ttu-id="3ae29-121">[GroupBy](./groupby-element-for-view-format.md)要素 (この例では示されていません) は、オブジェクトの新しいグループが表示されるタイミングを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-121">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="3ae29-122">特定のプロパティまたはスクリプトの値が変更されるたびに、新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-122">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="3ae29-123">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-123">This element is optional.</span></span>

- <span data-ttu-id="3ae29-124">[Controls](./controls-element-for-view-format.md)要素 (この例では示されていません) は、テーブルビューで定義されるカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-124">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="3ae29-125">コントロールを使用すると、データの表示方法をさらに指定することができます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-125">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="3ae29-126">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-126">This element is optional.</span></span> <span data-ttu-id="3ae29-127">ビューでは、独自のカスタムコントロールを定義することも、書式設定ファイルの任意のビューで使用できるコモンコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-127">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="3ae29-128">カスタムコントロールの詳細については、「 [カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae29-128">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="3ae29-129">[Hidetableheaders](./hidetableheaders-element-format.md)要素 (この例では示されていません) は、テーブルの先頭にラベルが表示されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-129">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="3ae29-130">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-130">This element is optional.</span></span>

- <span data-ttu-id="3ae29-131">テーブルのヘッダーと行の情報を定義する [Tablecontrol](./tablecontrol-element-format.md) 要素。</span><span class="sxs-lookup"><span data-stu-id="3ae29-131">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="3ae29-132">他のすべてのビューと同様に、テーブルビューでは、オブジェクトのプロパティの値や、スクリプトによって生成される値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-132">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="3ae29-133">列ヘッダーの定義</span><span class="sxs-lookup"><span data-stu-id="3ae29-133">Defining Column Headers</span></span>

1. <span data-ttu-id="3ae29-134">[Tableheaders](./tableheaders-element-format.md)要素とその子要素は、テーブルの上部に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-134">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="3ae29-135">[TableColumnHeader](./tablecolumnheader-element-format.md)要素は、テーブルの列の上部に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-135">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="3ae29-136">これらの要素は、ヘッダーを表示する順序で指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-136">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="3ae29-137">使用できる要素の数に制限はありませんが、テーブルビュー内の [TableColumnHeader](./tablecolumnheader-element-format.md) 要素の数は、使用する [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) 要素の数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae29-137">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="3ae29-138">[Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-138">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="3ae29-139">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-139">This element is optional.</span></span>

4. <span data-ttu-id="3ae29-140">[Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、列の幅 (文字数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-140">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="3ae29-141">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-141">This element is optional.</span></span>

5. <span data-ttu-id="3ae29-142">[Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、ラベルの表示方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-142">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="3ae29-143">ラベルは左、右、または中央に配置できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-143">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="3ae29-144">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-144">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="3ae29-145">テーブル行の定義</span><span class="sxs-lookup"><span data-stu-id="3ae29-145">Defining the Table Rows</span></span>

<span data-ttu-id="3ae29-146">テーブルビューでは、 [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) 要素の子要素を使用して、テーブルの行に表示されるデータを指定する1つ以上の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-146">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="3ae29-147">テーブルの行に対して複数の定義を指定できますが、使用されている行の定義に関係なく、行のヘッダーは同じままです。</span><span class="sxs-lookup"><span data-stu-id="3ae29-147">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="3ae29-148">通常、テーブルの定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="3ae29-148">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="3ae29-149">次の例では、ビューには、システムの複数のプロパティの値を表示する1つの定義が用意されています。 [Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3ae29-149">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="3ae29-150">テーブルビューでは、プロパティの値やスクリプトの値 (例では示されていません) を行に表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-150">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

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

<span data-ttu-id="3ae29-151">次の XML 要素を使用して、行の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-151">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="3ae29-152">[TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)要素とその子要素は、テーブルの行に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-152">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="3ae29-153">[TableRowEntry](./listentry-element-for-listcontrol-format.md)要素は、行の定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-153">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="3ae29-154">少なくとも1つの [TableRowEntry](./listentry-element-for-listcontrol-format.md) が必要です。ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-154">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="3ae29-155">ほとんどの場合、ビューには定義が1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-155">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="3ae29-156">[Entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-156">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="3ae29-157">この要素は省略可能であり、異なるオブジェクトを表示する複数の [TableRowEntry](./listentry-element-for-listcontrol-format.md) 要素を定義する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-157">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="3ae29-158">[Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)要素は、列幅を超えるテキストを次の行に表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-158">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="3ae29-159">既定では、列幅を超えるテキストは切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-159">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="3ae29-160">[TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)要素は、値が行に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-160">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="3ae29-161">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、値が行の列に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-161">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="3ae29-162">行の各列には [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) 要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-162">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="3ae29-163">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-163">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="3ae29-164">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-164">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="3ae29-165">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-165">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="3ae29-166">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-166">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="3ae29-167">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-167">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="3ae29-168">[FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-168">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="3ae29-169">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-169">This element is optional.</span></span>

- <span data-ttu-id="3ae29-170">[Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、プロパティまたはスクリプトの値の表示方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-170">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="3ae29-171">値は、左、右、または中央揃えに配置できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-171">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="3ae29-172">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-172">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="3ae29-173">テーブルビューを使用するオブジェクトの定義</span><span class="sxs-lookup"><span data-stu-id="3ae29-173">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="3ae29-174">テーブルビューを使用する .NET オブジェクトを定義するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3ae29-174">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="3ae29-175">[Viewselectedby](./viewselectedby-element-format.md)要素を使用すると、ビューのすべての定義で表示できるオブジェクトを定義できます。また、 [entryselectedby](./entryselectedby-element-for-listentry-for-listcontrol-format.md)要素を使用して、ビューの特定の定義によって表示されるオブジェクトを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-175">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="3ae29-176">ほとんどの場合、ビューには定義が1つしかないため、オブジェクトは通常、 [Viewselectedby](./viewselectedby-element-format.md) 要素によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-176">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="3ae29-177">次の例は、 [Viewselectedby](./viewselectedby-element-format.md) および [TypeName](./typename-element-for-viewselectedby-format.md) 要素を使用してテーブルビューに表示されるオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ae29-177">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="3ae29-178">指定できる [TypeName](./typename-element-for-viewselectedby-format.md) 要素の数に制限はありません。これらの要素の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-178">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="3ae29-179">次の XML 要素を使用して、テーブルビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-179">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="3ae29-180">[Viewselectedby](./viewselectedby-element-format.md)要素は、リストビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-180">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="3ae29-181">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .net オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-181">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="3ae29-182">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-182">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="3ae29-183">ビューには少なくとも1つの種類または選択セットを指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-183">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="3ae29-184">次の例では、 [Viewselectedby](./viewselectedby-element-format.md) 要素と [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-184">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="3ae29-185">複数のビューを使用して表示される関連オブジェクトのセットがある場合、たとえば、同じオブジェクトのリストビューやテーブルビューを定義するときに、選択セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-185">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="3ae29-186">選択セットを作成する方法の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae29-186">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="3ae29-187">次の XML 要素を使用して、リストビューで使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-187">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="3ae29-188">[Viewselectedby](./viewselectedby-element-format.md)要素は、リストビューによって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-188">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="3ae29-189">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、ビューで表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-189">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="3ae29-190">ビューには少なくとも1つの選択セットまたは型を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-190">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="3ae29-191">次の例では、 [Entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) 要素を使用して、テーブルビューの特定の定義によって表示されるオブジェクトを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-191">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="3ae29-192">この要素を使用して、オブジェクトの .NET 型名、選択したオブジェクトのセット、または定義を使用するタイミングを指定する選択条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-192">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="3ae29-193">選択条件を作成する方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae29-193">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3ae29-194">テーブルビューの複数の定義を作成する場合は、異なる列ヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-194">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="3ae29-195">表示するオブジェクトなど、テーブルの行に表示されるもののみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-195">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="3ae29-196">次の XML 要素を使用して、リストビューの特定の定義によって使用されるオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-196">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="3ae29-197">[Entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素は、定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-197">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="3ae29-198">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)要素は、定義によって表示される .net オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-198">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="3ae29-199">この要素を使用する場合は、完全修飾された .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-199">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="3ae29-200">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-200">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="3ae29-201">[SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)要素 (表示されません) は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-201">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="3ae29-202">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-202">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="3ae29-203">[Selectioncondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)要素 (表示されません) は、この定義を使用するために存在する必要がある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-203">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="3ae29-204">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-204">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="3ae29-205">選択条件の定義の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae29-205">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="3ae29-206">書式指定文字列の使用</span><span class="sxs-lookup"><span data-stu-id="3ae29-206">Using Format Strings</span></span>

<span data-ttu-id="3ae29-207">書式設定文字列をビューに追加して、データの表示方法をさらに定義できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-207">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="3ae29-208">次の例は、プロパティの値の書式設定文字列を定義する方法を示して `StartTime` います。</span><span class="sxs-lookup"><span data-stu-id="3ae29-208">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="3ae29-209">次の XML 要素を使用して、書式パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-209">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="3ae29-210">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、値が行の列に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-210">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="3ae29-211">行の各列には [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) 要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-211">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="3ae29-212">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-212">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="3ae29-213">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-213">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="3ae29-214">プロパティまたはスクリプトのどちらかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="3ae29-215">[FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-215">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="3ae29-216">次の例では、 `ToString` スクリプトの値の書式を設定するためにメソッドが呼び出されています。</span><span class="sxs-lookup"><span data-stu-id="3ae29-216">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="3ae29-217">スクリプトは、オブジェクトの任意のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-217">Scripts can call any method of an object.</span></span> <span data-ttu-id="3ae29-218">したがって、オブジェクトに、書式設定パラメーターを持つなどのメソッドがある場合、 `ToString` スクリプトはそのメソッドを呼び出してスクリプトの出力値を書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-218">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="3ae29-219">次の XML 要素を使用して、メソッドを呼び出すことができ `ToString` ます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-219">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="3ae29-220">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、値が行の列に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-220">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="3ae29-221">行の各列には [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) 要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae29-221">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="3ae29-222">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ae29-222">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="3ae29-223">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、値が行に表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ae29-223">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="3ae29-224">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ae29-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ae29-225">参照</span><span class="sxs-lookup"><span data-stu-id="3ae29-225">See Also</span></span>

[<span data-ttu-id="3ae29-226">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="3ae29-226">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
