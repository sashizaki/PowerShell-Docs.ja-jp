---
ms.date: 09/13/2016
ms.topic: reference
title: 書式設定ファイルの概要
description: 書式設定ファイルの概要
ms.openlocfilehash: 769a86d274ef3b35a322d76e2f03cb551d9204a1
ms.sourcegitcommit: 04faa7dc1122bce839295d4891bd8b2f0ecb06ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "97879138"
---
# <a name="formatting-file-overview"></a><span data-ttu-id="4edad-103">書式設定ファイルの概要</span><span class="sxs-lookup"><span data-stu-id="4edad-103">Formatting File Overview</span></span>

<span data-ttu-id="4edad-104">コマンドによって返されるオブジェクトの表示形式 (コマンドレット、関数、およびスクリプト) は、書式設定ファイル (format.ps1xml ファイル) を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="4edad-104">The display format for the objects that are returned by commands (cmdlets, functions, and scripts) are defined by using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="4edad-105">これらのファイルのいくつかは、powershell が提供するコマンドによって返されるオブジェクトの表示形式を定義するために PowerShell によって提供され [ます。たとえば](/dotnet/api/System.Diagnostics.Process) 、コマンドレットによって返される system.object オブジェクトなど `Get-Process` です。</span><span class="sxs-lookup"><span data-stu-id="4edad-105">Several of these files are provided by PowerShell to define the display format for those objects returned by PowerShell-provided commands, such as the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object returned by the `Get-Process` cmdlet.</span></span> <span data-ttu-id="4edad-106">ただし、独自のカスタム書式設定ファイルを作成して既定の表示形式を上書きすることも、独自のコマンドによって返されるオブジェクトの表示を定義するカスタム書式設定ファイルを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="4edad-106">However, you can also create your own custom formatting files to overwrite the default display formats or you can write a custom formatting file to define the display of objects returned by your own commands.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4edad-107">書式設定ファイルでは、パイプラインに返されるオブジェクトの要素は決定されません。</span><span class="sxs-lookup"><span data-stu-id="4edad-107">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="4edad-108">オブジェクトがパイプラインに返されると、一部のメンバーが表示されていない場合でも、そのオブジェクトのすべてのメンバーが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4edad-108">When an object is returned to the pipeline, all members of that object are available even if some are not displayed.</span></span>

<span data-ttu-id="4edad-109">PowerShell では、これらの書式設定ファイルのデータを使用して、表示される内容と、表示されるデータの書式設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="4edad-109">PowerShell uses the data in these formatting files to determine what is displayed and how the displayed data is formatted.</span></span> <span data-ttu-id="4edad-110">表示されるデータには、オブジェクトのプロパティやスクリプトの値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4edad-110">The displayed data can include the properties of an object or the value of a script.</span></span> <span data-ttu-id="4edad-111">スクリプトは、オブジェクトのプロパティから直接使用できない値を表示する場合に使用します。たとえば、オブジェクトの2つのプロパティの値を加算し、その合計をデータの一部として表示します。</span><span class="sxs-lookup"><span data-stu-id="4edad-111">Scripts are used if you want to display some value that is not available directly from the properties of an object, such as adding the value of two properties of an object and then displaying the sum as a piece of data.</span></span> <span data-ttu-id="4edad-112">表示されるデータの書式設定を行うには、表示するオブジェクトのビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="4edad-112">Formatting of the displayed data is done by defining views for the objects that you want to display.</span></span> <span data-ttu-id="4edad-113">各オブジェクトに対して1つのビューを定義したり、複数のオブジェクトに対して1つのビューを定義したり、同じオブジェクトに対して複数のビューを定義したりできます。</span><span class="sxs-lookup"><span data-stu-id="4edad-113">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="4edad-114">定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="4edad-114">There is no limit to the number of views that you can define.</span></span>

## <a name="common-features-of-formatting-files"></a><span data-ttu-id="4edad-115">フォーマットファイルの一般的な機能</span><span class="sxs-lookup"><span data-stu-id="4edad-115">Common Features of Formatting Files</span></span>

<span data-ttu-id="4edad-116">各フォーマットファイルでは、ファイルで定義されているすべてのビュー間で共有できる次のコンポーネントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4edad-116">Each formatting file can define the following components that can be shared across all the views defined by the file:</span></span>

- <span data-ttu-id="4edad-117">既定の構成設定 (テーブルの行に表示されるデータを、列の幅よりも長い場合に、次の行に表示するかどうかなど)。</span><span class="sxs-lookup"><span data-stu-id="4edad-117">Default configuration setting, such as whether the data displayed in the rows of tables will be displayed on the next line if the data is longer than the width of the column.</span></span> <span data-ttu-id="4edad-118">これらの設定の詳細については、「 [共通の構成設定の定義](./defining-common-configuration-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edad-118">For more information about these settings, see [Defining Common Configuration Settings](./defining-common-configuration-features.md).</span></span>

- <span data-ttu-id="4edad-119">書式設定ファイルのいずれかのビューで表示できるオブジェクトのセット。</span><span class="sxs-lookup"><span data-stu-id="4edad-119">Sets of objects that can be displayed by any of the views of the formatting file.</span></span> <span data-ttu-id="4edad-120">これらのセット ( *選択セット* と呼ばれます) の詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edad-120">For more information about these sets (referred to as *selection sets*), see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

- <span data-ttu-id="4edad-121">書式設定ファイルのすべてのビューで使用できるコモンコントロール。</span><span class="sxs-lookup"><span data-stu-id="4edad-121">Common controls that can be used by all the views of the formatting file.</span></span> <span data-ttu-id="4edad-122">コントロールを使用すると、データの表示方法をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="4edad-122">Controls give you finer control on how data is displayed.</span></span> <span data-ttu-id="4edad-123">コントロールの詳細については、「 [カスタムコントロールの定義](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edad-123">For more information about controls, see [Defining Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="formatting-views"></a><span data-ttu-id="4edad-124">ビューの書式設定</span><span class="sxs-lookup"><span data-stu-id="4edad-124">Formatting Views</span></span>

<span data-ttu-id="4edad-125">書式設定ビューでは、オブジェクトをテーブル形式、リスト形式、ワイド形式、およびカスタム書式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="4edad-125">Formatting views can display objects in a table format, list format, wide format, and custom format.</span></span> <span data-ttu-id="4edad-126">ほとんどの場合、各書式設定定義は、ビューを記述する XML タグのセットによって記述されます。</span><span class="sxs-lookup"><span data-stu-id="4edad-126">For the most part, each formatting definition is described by a set of XML tags that describe the view.</span></span> <span data-ttu-id="4edad-127">各ビューには、ビューの名前、ビューを使用するオブジェクト、およびテーブルビューの列と行の情報など、ビューの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4edad-127">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="4edad-128">テーブルビューには、1つまたは複数の列にオブジェクトまたはスクリプトブロックの値のプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4edad-128">Table View Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="4edad-129">各列は、オブジェクトまたはスクリプト値の単一のプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="4edad-129">Each column represents a single property of the object or a script value.</span></span> <span data-ttu-id="4edad-130">オブジェクトのすべてのプロパティ、オブジェクトのプロパティのサブセット、またはプロパティとスクリプト値の組み合わせを表示するテーブルビューを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4edad-130">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script values.</span></span> <span data-ttu-id="4edad-131">テーブルの各行は、返されたオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="4edad-131">Each row of the table represents a returned object.</span></span> <span data-ttu-id="4edad-132">テーブルビューの作成は、オブジェクトをコマンドレットにパイプする場合とよく似てい `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="4edad-132">Creating a table view is very similar to when you pipe an object to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="4edad-133">このビューの詳細については、「 [テーブルビュー](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edad-133">For more information about this view, see [Table View](./creating-a-table-view.md).</span></span>

<span data-ttu-id="4edad-134">リストビューには、1つの列にオブジェクトまたはスクリプトの値のプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4edad-134">List View Lists the properties of an object or a script value in a single column.</span></span> <span data-ttu-id="4edad-135">一覧の各行には、省略可能なラベルまたはプロパティ名の後にプロパティまたはスクリプトの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4edad-135">Each row of the list displays an optional label or the property name followed by the value of the property or script.</span></span> <span data-ttu-id="4edad-136">リストビューを作成することは、オブジェクトをコマンドレットにパイプすることとよく似てい `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="4edad-136">Creating a list view is very similar to piping an object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="4edad-137">このビューの詳細については、「 [リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edad-137">For more information about this view, see [List View](./creating-a-list-view.md).</span></span>

<span data-ttu-id="4edad-138">[ワイドビュー] オブジェクトの1つのプロパティまたは1つ以上の列のスクリプト値を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="4edad-138">Wide View Lists a single property of an object or a script value in one or more columns.</span></span> <span data-ttu-id="4edad-139">このビューにはラベルまたはヘッダーがありません。</span><span class="sxs-lookup"><span data-stu-id="4edad-139">There is no label or header for this view.</span></span> <span data-ttu-id="4edad-140">ワイドビューを作成することは、オブジェクトをコマンドレットにパイプすることとよく似てい `Format-Wide` ます。</span><span class="sxs-lookup"><span data-stu-id="4edad-140">Creating a wide view is very similar to piping an object to the `Format-Wide` cmdlet.</span></span> <span data-ttu-id="4edad-141">このビューの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edad-141">For more information about this view, see [Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="4edad-142">[カスタムビュー] テーブルビュー、リストビュー、またはワイドビューの固定構造に準拠していないオブジェクトプロパティまたはスクリプト値のカスタマイズ可能なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4edad-142">Custom View Displays a customizable view of object properties or script values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="4edad-143">スタンドアロンのカスタムビューを定義することも、テーブルビューやリストビューなどの別のビューで使用されるカスタムビューを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="4edad-143">You can define a stand-alone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="4edad-144">カスタムビューを作成することは、オブジェクトをコマンドレットにパイプすることとよく似てい `Format-Custom` ます。</span><span class="sxs-lookup"><span data-stu-id="4edad-144">Creating a custom view is very similar to piping an object to the `Format-Custom` cmdlet.</span></span> <span data-ttu-id="4edad-145">このビューの詳細については、「 [カスタムビュー](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edad-145">For more information about this view, see [Custom View](./creating-custom-controls.md).</span></span>

## <a name="components-of-a-view"></a><span data-ttu-id="4edad-146">ビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="4edad-146">Components of a View</span></span>

<span data-ttu-id="4edad-147">次の XML の例は、ビューの基本的な XML コンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="4edad-147">The following XML examples show the basic XML components of a view.</span></span> <span data-ttu-id="4edad-148">個々の XML 要素は、どのビューを作成するかによって異なりますが、ビューの基本コンポーネントはすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="4edad-148">The individual XML elements vary depending on which view you want to create, but the basic components of the views are all the same.</span></span>

<span data-ttu-id="4edad-149">最初に、各ビューには、 `Name` ビューを参照するために使用されるユーザーフレンドリ名を指定する要素があります。</span><span class="sxs-lookup"><span data-stu-id="4edad-149">To start with, each view has a `Name` element that specifies a user friendly name that is used to reference the view.</span></span> <span data-ttu-id="4edad-150">`ViewSelectedBy`ビューによって表示される .net オブジェクトと、ビューを定義する *コントロール* 要素を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="4edad-150">a `ViewSelectedBy` element that defines which .NET objects are displayed by the view, and a *control* element that defines the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <ListControl>...</ListControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <WideControl>...</WideControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <CustomControl>...</CustomControl>
  </View>
</ViewDefinitions>

```

<span data-ttu-id="4edad-151">Control 要素内では、1つまたは複数の *エントリ* 要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="4edad-151">Within the control element, you can define one or more *entry* elements.</span></span> <span data-ttu-id="4edad-152">複数の定義を使用する場合は、各定義を使用する .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4edad-152">If you use multiple definitions, you must specify which .NET objects use each definition.</span></span> <span data-ttu-id="4edad-153">通常、各コントロールに必要なエントリは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="4edad-153">Typically only one entry, with only one definition, is needed for each control.</span></span>

```xml
<ListControl>
  <ListEntries>
    <ListEntry>
      <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
  </ListEntries>
</ListControl>

```

<span data-ttu-id="4edad-154">ビューの各エントリ要素内で、そのビューによって表示される .NET プロパティまたはスクリプトを定義する *項目* 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edad-154">Within each entry element of a view, you specify the *item* elements that define the .NET properties or scripts that are displayed by that view.</span></span>

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

<span data-ttu-id="4edad-155">前の例で示したように、書式設定ファイルには複数のビューを含めることができます。ビューには複数の定義を含めることができ、各定義には複数の項目を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4edad-155">As shown in the preceding examples, the formatting file can contain multiple views, a view can contain multiple definitions, and each definition can contain multiple items.</span></span>

## <a name="example-of-a-table-view"></a><span data-ttu-id="4edad-156">テーブルビューの例</span><span class="sxs-lookup"><span data-stu-id="4edad-156">Example of a Table View</span></span>

<span data-ttu-id="4edad-157">次の例は、2つの列を含むテーブルビューを定義するために使用される XML タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="4edad-157">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="4edad-158">[Viewdefinitions](./viewdefinitions-element-format.md)要素は、書式設定ファイルで定義されているすべてのビューのコンテナー要素です。</span><span class="sxs-lookup"><span data-stu-id="4edad-158">The [ViewDefinitions](./viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="4edad-159">[View](./view-element-format.md)要素は、特定のテーブル、リスト、ワイド、またはカスタムビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="4edad-159">The [View](./view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="4edad-160">各 [ビュー](./view-element-format.md) 要素内では、 [name](./name-element-for-view-format.md) 要素はビューの名前を指定し、 [viewselectedby](./viewselectedby-element-format.md) 要素はビューを使用するオブジェクトを定義します。また、次の例に示すように、さまざまなコントロール要素が `TableControl` ビューの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="4edad-160">Within each [View](./view-element-format.md) element, the [Name](./name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element shown in the following example) define the type of the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="4edad-161">参照</span><span class="sxs-lookup"><span data-stu-id="4edad-161">See Also</span></span>

[<span data-ttu-id="4edad-162">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="4edad-162">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4edad-163">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="4edad-163">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4edad-164">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="4edad-164">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4edad-165">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="4edad-165">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="4edad-166">PowerShell の形式と種類のファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4edad-166">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
