---
title: テーブル ビューを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f405afb-70b5-4fe0-9986-bc07401d93fd
caps.latest.revision: 23
ms.openlocfilehash: 832527ea4b042812c39934cd7e124201c6dc2ea4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861498"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="4a083-102">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="4a083-102">Creating a Table View</span></span>

<span data-ttu-id="4a083-103">テーブル ビューでは、1 つまたは複数の列のデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="4a083-103">A table view displays data in one or more columns.</span></span> <span data-ttu-id="4a083-104">テーブル内の各行は、.NET オブジェクトを表し、テーブルの各列は、オブジェクトまたはスクリプトの値のプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="4a083-104">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="4a083-105">オブジェクトのすべてのプロパティまたはオブジェクトのプロパティのサブセットを表示するテーブルのビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="4a083-105">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="4a083-106">テーブル ビューの表示</span><span class="sxs-lookup"><span data-stu-id="4a083-106">A Table View Display</span></span>

<span data-ttu-id="4a083-107">次の例は、Windows PowerShell を表示する方法を示しています、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトによって返される、 [Get-service](/powershell/module/microsoft.powershell.management/get-service)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="4a083-107">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="4a083-108">Windows PowerShell には、このオブジェクトのテーブルに表示するビューが定義されて、`Status`プロパティ、`Name`プロパティ (このプロパティは、エイリアス プロパティを`ServiceName`プロパティ)、および`DisplayName`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4a083-108">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="4a083-109">テーブル内の各行は、コマンドレットによって返されるオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="4a083-109">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="4a083-110">テーブル ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-110">Defining the Table View</span></span>

<span data-ttu-id="4a083-111">次の XML は、テーブル ビューのスキーマを表示するため、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4a083-111">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="4a083-112">テーブル ビューで表示する各プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a083-112">You must specify each property that you want displayed in the table view.</span></span>

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

<span data-ttu-id="4a083-113">次の XML 要素は、リスト ビューの定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a083-113">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="4a083-114">[ビュー](./view-element-format.md)要素は、テーブル ビューの親要素です。</span><span class="sxs-lookup"><span data-stu-id="4a083-114">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="4a083-115">(これは、一覧、幅をカスタム コントロールの表示については、同じ親要素です)。</span><span class="sxs-lookup"><span data-stu-id="4a083-115">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="4a083-116">[名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-116">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="4a083-117">この要素は、すべてのビューに必要です。</span><span class="sxs-lookup"><span data-stu-id="4a083-117">This element is required for all views.</span></span>

- <span data-ttu-id="4a083-118">[ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-118">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="4a083-119">この要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a083-119">This element is required.</span></span>

- <span data-ttu-id="4a083-120">[GroupBy](./groupby-element-for-view-format.md)オブジェクトの新しいグループが表示される場合 (この例では説明しません) 要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-120">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="4a083-121">特定のプロパティまたはスクリプトの値が変更されるたびに新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="4a083-121">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="4a083-122">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-122">This element is optional.</span></span>

- <span data-ttu-id="4a083-123">[コントロール](./controls-element-for-view-format.md)要素 (この例では表示されません)、テーブル ビューで定義されているカスタム コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-123">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="4a083-124">コントロールでは、さらに、データの表示方法を指定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a083-124">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="4a083-125">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-125">This element is optional.</span></span> <span data-ttu-id="4a083-126">ビューがその独自のカスタム コントロールを定義できます。 または書式設定ファイルに任意のビューで使用できる一般的なコントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-126">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="4a083-127">カスタム コントロールの詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a083-127">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="4a083-128">[HideTableHeaders](./hidetableheaders-element-format.md)要素 (この例では表示されません) では、テーブルでは、テーブルの上部にある任意のラベルは表示されませんを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-128">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="4a083-129">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-129">This element is optional.</span></span>

- <span data-ttu-id="4a083-130">[TableControl](./tablecontrol-element-format.md)テーブルのヘッダーと行情報を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-130">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="4a083-131">その他のすべてのビューと同様に、テーブル ビューを表示できますオブジェクトのプロパティの値またはスクリプトによって生成される値。</span><span class="sxs-lookup"><span data-stu-id="4a083-131">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="4a083-132">列ヘッダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-132">Defining Column Headers</span></span>

1. <span data-ttu-id="4a083-133">[TableHeaders](./tableheaders-element-format.md)要素とその子要素は、テーブルの上部に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-133">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="4a083-134">[TableColumnHeader](./tablecolumnheader-element-format.md)要素は、テーブルの列の上部に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-134">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="4a083-135">ヘッダーを表示する順序でこれらの要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-135">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="4a083-136">数は、次のように使用できる、これらの要素の数に制限はありません[TableColumnHeader](./tablecolumnheader-element-format.md)テーブル ビュー内の要素の数に一致する必要があります[TableRowEntry](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)を使用する要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-136">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="4a083-137">[ラベル](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)要素が表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-137">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="4a083-138">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-138">This element is optional.</span></span>

4. <span data-ttu-id="4a083-139">[幅](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)要素 (文字) で、列の幅を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-139">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="4a083-140">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-140">This element is optional.</span></span>

5. <span data-ttu-id="4a083-141">[配置](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)要素は、ラベルを表示する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-141">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="4a083-142">ラベルの右側に、左側に配置または中央に配置できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-142">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="4a083-143">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-143">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="4a083-144">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-144">Defining the Table Rows</span></span>

<span data-ttu-id="4a083-145">テーブル ビューでの子要素を使用して、どのようなデータをテーブルの行に表示を指定する 1 つまたは複数の定義を提供できます、 [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-145">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="4a083-146">テーブルの行に対して複数の定義を指定できますが、行のヘッダーはどのような行定義の使用に関係なく、同じことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a083-146">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="4a083-147">通常、テーブルには、1 つだけ定義があります。</span><span class="sxs-lookup"><span data-stu-id="4a083-147">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="4a083-148">ビューでのいくつかのプロパティの値を表示する 1 つの定義は、次の例では、 [System.Diagnostics.Process でしょうか。Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4a083-148">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="4a083-149">テーブル ビューでは、その行のプロパティの値またはスクリプト (この例では表示されません) の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-149">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

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

<span data-ttu-id="4a083-150">行の定義を提供する、次の XML 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-150">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="4a083-151">[TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md)要素とその子要素は、テーブルの行に表示される内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-151">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="4a083-152">[TableRowEntry](./listentry-element-for-listcontrol-format.md)要素は、行の定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a083-152">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="4a083-153">少なくとも 1 つ[TableRowEntry](./listentry-element-for-listcontrol-format.md)が必要です。 ただし、追加できる要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="4a083-153">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="4a083-154">ほとんどの場合、ビューは 1 つだけ定義になります。</span><span class="sxs-lookup"><span data-stu-id="4a083-154">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="4a083-155">[EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素は、特定の定義によって表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-155">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="4a083-156">この要素は省略可能と複数を定義する場合にのみ必要です[TableRowEntry](./listentry-element-for-listcontrol-format.md)さまざまなオブジェクトを表示する要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-156">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="4a083-157">[ラップ](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)要素は、次の行を列の幅を超えるテキストが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-157">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrl-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="4a083-158">既定では、列幅を超えるテキストは切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="4a083-158">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="4a083-159">[TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)プロパティまたはスクリプトの行の表示が値を持つ要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-159">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="4a083-160">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)プロパティまたは値を持つが、行の列に表示されているスクリプト要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-160">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="4a083-161">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、行の各列は必須です。</span><span class="sxs-lookup"><span data-stu-id="4a083-161">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="4a083-162">最初のエントリには、最初の列、列と 2 番目の上から 2 番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a083-162">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="4a083-163">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-163">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="4a083-164">プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a083-164">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="4a083-165">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-165">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="4a083-166">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a083-166">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="4a083-167">[FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-167">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="4a083-168">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-168">This element is optional.</span></span>

- <span data-ttu-id="4a083-169">[配置](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)要素は、プロパティ、またはスクリプトの値を表示する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-169">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="4a083-170">値の右側に、左側に配置または中央に配置できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-170">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="4a083-171">この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a083-171">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="4a083-172">テーブル ビューを使用するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-172">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="4a083-173">.NET オブジェクトを使用して、テーブル ビューを定義する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="4a083-173">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="4a083-174">使用することができます、 [ViewSelectedBy](./viewselectedby-element-format.md)するか、ビューのすべての定義を表示できるオブジェクトを定義する要素を使用できる、 [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md)によって表示されるオブジェクトを定義する要素、ビューの定義を特定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-174">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="4a083-175">ほとんどの場合、ビューでは 1 つだけ定義は、オブジェクトは通常で定義されるため、 [ViewSelectedBy](./viewselectedby-element-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-175">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="4a083-176">次の例は、テーブルのビューを使用して表示されるオブジェクトを定義する方法を示します、 [ViewSelectedBy](./viewselectedby-element-format.md)と[TypeName](./typename-element-for-viewselectedby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-176">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="4a083-177">数に制限はありません[TypeName](./typename-element-for-viewselectedby-format.md)要素を指定できますが、およびその順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="4a083-177">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="4a083-178">次の XML 要素を使用して、テーブル ビューで使用されるオブジェクトを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4a083-178">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="4a083-179">[ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-179">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="4a083-180">[TypeName](./typename-element-for-viewselectedby-format.md)要素は、ビューによって表示される .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-180">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="4a083-181">完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a083-181">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="4a083-182">少なくとも 1 つの型またはビューの設定の選択範囲を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="4a083-182">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="4a083-183">次の例では、 [ViewSelectedBy](./viewselectedby-element-format.md)と[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-183">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="4a083-184">関連する一連の同じオブジェクトのリスト ビューを定義する場合など、複数のビューおよびテーブル ビューを使用して表示されるオブジェクトがある選択範囲のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a083-184">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="4a083-185">選択範囲のセットを作成する方法の詳細については、次を参照してください。[選択範囲のセットを定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a083-185">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="4a083-186">次の XML 要素を使用して、リスト ビューで使用されるオブジェクトを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4a083-186">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="4a083-187">[ViewSelectedBy](./viewselectedby-element-format.md)要素がリスト ビューで表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-187">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="4a083-188">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md)要素は、一連のビューで表示できるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-188">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="4a083-189">少なくとも 1 つの選択範囲のセットまたはビューの種類を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="4a083-189">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="4a083-190">次の例は、ビューを使用してテーブルの特定の定義で表示されるオブジェクトを定義する方法を示します、 [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="4a083-190">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="4a083-191">この要素を使用して、オブジェクト、オブジェクトの選択範囲のセットまたは定義を使用する場合を指定する選択条件の .NET 型名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-191">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="4a083-192">選択条件を作成する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a083-192">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4a083-193">テーブル ビューの複数の定義を作成するときに、別の列ヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a083-193">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="4a083-194">どのようなオブジェクトが表示されるなど、テーブルの行に表示される内容のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-194">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="4a083-195">リスト ビューの特定の定義で使用されるオブジェクトを指定する、次の XML 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-195">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="4a083-196">[EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)要素定義によって表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-196">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="4a083-197">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md)要素を定義して表示されている .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-197">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="4a083-198">この要素を使用する場合は、完全修飾 .NET 型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a083-198">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="4a083-199">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="4a083-199">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="4a083-200">[SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義で表示できるオブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-200">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="4a083-201">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="4a083-201">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="4a083-202">[SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (表示されない) 要素は、この定義を使用するのに必要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-202">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="4a083-203">少なくとも 1 つの型、選択範囲のセット、または定義については、選択条件を指定する必要がありますが、指定できる要素の最大数はありません。</span><span class="sxs-lookup"><span data-stu-id="4a083-203">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="4a083-204">選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a083-204">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="4a083-205">書式指定文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a083-205">Using Format Strings</span></span>

<span data-ttu-id="4a083-206">さらに、データの表示方法を定義するビューには、書式設定文字列を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4a083-206">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="4a083-207">次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4a083-207">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="4a083-208">次の XML 要素を使用して、書式パターンを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4a083-208">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="4a083-209">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)プロパティまたは値を持つが、行の列に表示されているスクリプト要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-209">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="4a083-210">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、行の各列は必須です。</span><span class="sxs-lookup"><span data-stu-id="4a083-210">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="4a083-211">最初のエントリには、最初の列、列と 2 番目の上から 2 番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a083-211">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="4a083-212">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-212">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="4a083-213">プロパティまたはスクリプトのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a083-213">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="4a083-214">[FormatString](./label-element-for-listitem-for-listcontrol-format.md)要素は、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-214">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="4a083-215">次の例では、`ToString`スクリプトの値の書式設定メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4a083-215">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="4a083-216">スクリプトでは、オブジェクトのすべてのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4a083-216">Scripts can call any method of an object.</span></span> <span data-ttu-id="4a083-217">そのため、オブジェクトが、メソッドがなど`ToString`、書式設定パラメーターを持つ、スクリプトは、スクリプトの出力値の書式を指定するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4a083-217">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="4a083-218">次の XML 要素を呼び出すことができます、`ToString`メソッド。</span><span class="sxs-lookup"><span data-stu-id="4a083-218">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="4a083-219">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)プロパティまたは値を持つが、行の列に表示されているスクリプト要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a083-219">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="4a083-220">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)要素は、行の各列は必須です。</span><span class="sxs-lookup"><span data-stu-id="4a083-220">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="4a083-221">最初のエントリには、最初の列、列と 2 番目の上から 2 番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a083-221">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="4a083-222">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)要素の値が行に表示するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a083-222">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="4a083-223">スクリプトまたはプロパティのいずれかを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a083-223">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a083-224">参照</span><span class="sxs-lookup"><span data-stu-id="4a083-224">See Also</span></span>

[<span data-ttu-id="4a083-225">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="4a083-225">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
