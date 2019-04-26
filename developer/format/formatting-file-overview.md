---
title: ファイルの概要を書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe888fee-1fe9-459f-9d62-35732c19a7f8
caps.latest.revision: 13
ms.openlocfilehash: d418cff70c1197aa3c331eed909f49198da139e9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065735"
---
# <a name="formatting-file-overview"></a><span data-ttu-id="0f43d-102">書式設定ファイルの概要</span><span class="sxs-lookup"><span data-stu-id="0f43d-102">Formatting File Overview</span></span>

<span data-ttu-id="0f43d-103">コマンド (コマンドレット、関数、およびスクリプト) によって返されるオブジェクトの表示形式は、書式設定ファイル (format.ps1xml ファイル) を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-103">The display format for the objects that are returned by commands (cmdlets, functions, and scripts) are defined by using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="0f43d-104">などの PowerShell で提供されるコマンドによって返されるこれらのオブジェクトの表示形式を定義する PowerShell によって提供されるこれらのファイルのいくつか、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)によって返されるオブジェクト、`Get-Process`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="0f43d-104">Several of these files are provided by PowerShell to define the display format for those objects returned by PowerShell-provided commands, such as the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object returned by the `Get-Process` cmdlet.</span></span> <span data-ttu-id="0f43d-105">ただし、既定の表示形式を上書きする独自のカスタムの書式設定ファイルを作成することもできます。 または、独自のコマンドによって返されるオブジェクトの表示を定義するカスタムの書式設定ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-105">However, you can also create your own custom formatting files to overwrite the default display formats or you can write a custom formatting file to define the display of objects returned by your own commands.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f43d-106">書式設定ファイルは、パイプラインに返されるオブジェクトの要素を特定できません。</span><span class="sxs-lookup"><span data-stu-id="0f43d-106">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="0f43d-107">パイプラインにオブジェクトが返されると、そのオブジェクトのすべてのメンバーは、いくつかが表示されない場合でも使用です。</span><span class="sxs-lookup"><span data-stu-id="0f43d-107">When an object is returned to the pipeline, all members of that object are available even if some are not displayed.</span></span>

<span data-ttu-id="0f43d-108">PowerShell では、これらの書式設定ファイルでデータを使用して、表示される内容と表示されるデータの書式設定方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-108">PowerShell uses the data in these formatting files to determine what is displayed and how the displayed data is formatted.</span></span> <span data-ttu-id="0f43d-109">表示されるデータには、スクリプトの値またはオブジェクトのプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-109">The displayed data can include the properties of an object or the value of a script.</span></span> <span data-ttu-id="0f43d-110">スクリプトは、オブジェクトの 2 つのプロパティの値を追加して、データの一部として合計を表示するなどのオブジェクトのプロパティから直接は使用できないいくつかの値を表示する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-110">Scripts are used if you want to display some value that is not available directly from the properties of an object, such as adding the value of two properties of an object and then displaying the sum as a piece of data.</span></span> <span data-ttu-id="0f43d-111">表示されるデータの書式設定は、表示するオブジェクトのビューを定義することで行われます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-111">Formatting of the displayed data is done by defining views for the objects that you want to display.</span></span> <span data-ttu-id="0f43d-112">オブジェクトごとに 1 つのビューを定義することができます、複数のオブジェクトの 1 つのビューを定義することができます、または同じオブジェクトに対して複数のビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-112">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="0f43d-113">定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="0f43d-113">There is no limit to the number of views that you can define.</span></span>

## <a name="common-features-of-formatting-files"></a><span data-ttu-id="0f43d-114">書式設定ファイルの一般的な機能</span><span class="sxs-lookup"><span data-stu-id="0f43d-114">Common Features of Formatting Files</span></span>

<span data-ttu-id="0f43d-115">各書式設定ファイルには、ファイルで定義されているすべてのビューで共有できる、次のコンポーネントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-115">Each formatting file can define the following components that can be shared across all the views defined by the file:</span></span>

- <span data-ttu-id="0f43d-116">既定の構成設定、かどうかのテーブルの行に表示されるデータが次の行に表示されます、データが列の幅より長い場合など。</span><span class="sxs-lookup"><span data-stu-id="0f43d-116">Default configuration setting, such as whether the data displayed in the rows of tables will be displayed on the next line if the data is longer than the width of the column.</span></span> <span data-ttu-id="0f43d-117">これらの設定の詳細については、次を参照してください。[共通の構成設定を定義する](./defining-common-configuration-features.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-117">For more information about these settings, see [Defining Common Configuration Settings](./defining-common-configuration-features.md).</span></span>

- <span data-ttu-id="0f43d-118">書式設定ファイルのビューのいずれかで表示できるオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-118">Sets of objects that can be displayed by any of the views of the formatting file.</span></span> <span data-ttu-id="0f43d-119">これらのセットの詳細については (と呼ばれる*選択セット*) を参照してください[オブジェクト設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-119">For more information about these sets (referred to as *selection sets*), see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

- <span data-ttu-id="0f43d-120">書式設定ファイルのすべてのビューで使用できる一般的なコントロール。</span><span class="sxs-lookup"><span data-stu-id="0f43d-120">Common controls that can be used by all the views of the formatting file.</span></span> <span data-ttu-id="0f43d-121">コントロールでは、データの表示方法の詳細な制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-121">Controls give you finer control on how data is displayed.</span></span> <span data-ttu-id="0f43d-122">コントロールの詳細については、次を参照してください。[カスタム コントロールの定義と](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-122">For more information about controls, see [Defining Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="formatting-views"></a><span data-ttu-id="0f43d-123">書式設定のビュー</span><span class="sxs-lookup"><span data-stu-id="0f43d-123">Formatting Views</span></span>

<span data-ttu-id="0f43d-124">書式設定のビューは、テーブル形式、一覧の形式、ワイド形式、およびカスタム形式でオブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-124">Formatting views can display objects in a table format, list format, wide format, and custom format.</span></span> <span data-ttu-id="0f43d-125">ほとんどの場合、各書式設定の定義は、一連のビューを記述する XML タグで表されます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-125">For the most part, each formatting definition is described by a set of XML tags that describe the view.</span></span> <span data-ttu-id="0f43d-126">それぞれのビューには、ビュー、およびテーブル ビューの列と行情報など、ビューの要素を使用するオブジェクトには、ビューの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f43d-126">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="0f43d-127">テーブル ビューまたはスクリプト ブロックの値を 1 つまたは複数の列内のオブジェクトのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-127">Table View Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="0f43d-128">各列は、オブジェクトまたはスクリプトの値の 1 つのプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-128">Each column represents a single property of the object or a script value.</span></span> <span data-ttu-id="0f43d-129">オブジェクト、オブジェクト、またはプロパティとスクリプトの値の組み合わせのプロパティのサブセットのすべてのプロパティを表示するテーブルのビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-129">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script values.</span></span> <span data-ttu-id="0f43d-130">テーブルの各行は、返されたオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-130">Each row of the table represents a returned object.</span></span> <span data-ttu-id="0f43d-131">テーブル ビューを作成にオブジェクトをパイプするときによく似ています、`Format-Table`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="0f43d-131">Creating a table view is very similar to when you pipe an object to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="0f43d-132">このビューの詳細については、次を参照してください。[テーブル ビュー](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-132">For more information about this view, see [Table View](./creating-a-table-view.md).</span></span>

<span data-ttu-id="0f43d-133">リスト ビュー オブジェクトまたはスクリプトの値が 1 つの列のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-133">List View Lists the properties of an object or a script value in a single column.</span></span> <span data-ttu-id="0f43d-134">リストの各行には、オプションのラベルまたはプロパティ名の後に、プロパティやスクリプトの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-134">Each row of the list displays an optional label or the property name followed by the value of the property or script.</span></span> <span data-ttu-id="0f43d-135">リスト ビューを作成するオブジェクトをパイプするよく似ています、`Format-List`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="0f43d-135">Creating a list view is very similar to piping an object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="0f43d-136">このビューの詳細については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-136">For more information about this view, see [List View](./creating-a-list-view.md).</span></span>

<span data-ttu-id="0f43d-137">ワイド ビューには、1 つまたは複数の列でスクリプトの値またはオブジェクトの 1 つのプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-137">Wide View Lists a single property of an object or a script value in one or more columns.</span></span> <span data-ttu-id="0f43d-138">ラベルまたはこのビューのヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="0f43d-138">There is no label or header for this view.</span></span> <span data-ttu-id="0f43d-139">オブジェクトをパイプ処理とよく似ていますワイド ビューの作成、`Format-Wide`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="0f43d-139">Creating a wide view is very similar to piping an object to the `Format-Wide` cmdlet.</span></span> <span data-ttu-id="0f43d-140">このビューの詳細については、次を参照してください。[表示幅が広い](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-140">For more information about this view, see [Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="0f43d-141">カスタム ビューには、テーブルのビュー、リスト ビュー、またはワイド ビューの厳格な構造に準拠していないオブジェクトのプロパティやスクリプトの値のカスタマイズ可能なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-141">Custom View Displays a customizable view of object properties or script values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="0f43d-142">スタンドアロンのカスタム ビューを定義する、またはテーブル ビューまたはリスト ビューなどの別のビューで使用されるカスタム ビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-142">You can define a stand-alone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="0f43d-143">オブジェクトをパイプ処理とよく似ています、カスタム ビューの作成、`Format-Custom`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="0f43d-143">Creating a custom view is very similar to piping an object to the `Format-Custom` cmdlet.</span></span> <span data-ttu-id="0f43d-144">このビューの詳細については、次を参照してください。[カスタム ビュー](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-144">For more information about this view, see [Custom View](./creating-custom-controls.md).</span></span>

## <a name="components-of-a-view"></a><span data-ttu-id="0f43d-145">ビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="0f43d-145">Components of a View</span></span>

<span data-ttu-id="0f43d-146">次の XML の例では、ビューの基本的な XML コンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-146">The following XML examples show the basic XML components of a view.</span></span> <span data-ttu-id="0f43d-147">個々 の XML 要素は、作成するどのビューに応じてを異なりますが、ビューの基本コンポーネントはすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="0f43d-147">The individual XML elements vary depending on which view you want to create, but the basic components of the views are all the same.</span></span>

<span data-ttu-id="0f43d-148">最初に、各ビューでは、`Name`ビューを参照するために使用するユーザー フレンドリ名を指定する要素。</span><span class="sxs-lookup"><span data-stu-id="0f43d-148">To start with, each view has a `Name` element that specifies a user friendly name that is used to reference the view.</span></span> <span data-ttu-id="0f43d-149">`ViewSelectedBy` 、ビューによって表示される .NET オブジェクトを定義する要素と*コントロール*ビューを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="0f43d-149">a `ViewSelectedBy` element that defines which .NET objects are displayed by the view, and a *control* element that defines the view.</span></span>

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

<span data-ttu-id="0f43d-150">1 つまたは複数を定義するコントロール要素内で*エントリ*要素。</span><span class="sxs-lookup"><span data-stu-id="0f43d-150">Within the control element, you can define one or more *entry* elements.</span></span> <span data-ttu-id="0f43d-151">複数の定義を使用する場合は、.NET オブジェクトを使用して、それぞれの定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f43d-151">If you use multiple definitions, you must specify which .NET objects use each definition.</span></span> <span data-ttu-id="0f43d-152">通常、各コントロールの 1 つだけの定義と、1 つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f43d-152">Typically only one entry, with only one definition, is needed for each control.</span></span>

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

<span data-ttu-id="0f43d-153">指定したビューの各エントリ要素内で、*項目*.NET プロパティまたはそのビューによって表示されるスクリプトを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="0f43d-153">Within each entry element of a view, you specify the *item* elements that define the .NET properties or scripts that are displayed by that view.</span></span>

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

<span data-ttu-id="0f43d-154">上記の例に示すように書式設定ファイルが複数のビューを含めることができます、ビューは、複数の定義を含めることができますおよび各定義は複数の項目を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0f43d-154">As shown in the preceding examples, the formatting file can contain multiple views, a view can contain multiple definitions, and each definition can contain multiple items.</span></span>

## <a name="example-of-a-table-view"></a><span data-ttu-id="0f43d-155">テーブル ビューの例</span><span class="sxs-lookup"><span data-stu-id="0f43d-155">Example of a Table View</span></span>

<span data-ttu-id="0f43d-156">次の例は、2 つの列を含むテーブルのビューを定義するために使用する XML タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="0f43d-156">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="0f43d-157">[ViewDefinitions](./viewdefinitions-element-format.md)要素が書式設定ファイルで定義されているすべてのビューのコンテナー要素。</span><span class="sxs-lookup"><span data-stu-id="0f43d-157">The [ViewDefinitions](./viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="0f43d-158">[ビュー](./view-element-format.md)要素は、特定のテーブル、リスト、ビュー、またはカスタム ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-158">The [View](./view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="0f43d-159">各[ビュー](./view-element-format.md)要素、[名前](./name-element-for-view-format.md)要素は、ビューの名前を指定します、 [ViewSelectedBy](./viewselectedby-element-format.md)要素は、ビュー、およびさまざまなを使用するオブジェクトを定義します。コントロールの要素 (など、`TableControl`要素の次の例に示すように)、ビューの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-159">Within each [View](./view-element-format.md) element, the [Name](./name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element shown in the following example) define the type of the view.</span></span>

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
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="0f43d-160">参照</span><span class="sxs-lookup"><span data-stu-id="0f43d-160">See Also</span></span>

[<span data-ttu-id="0f43d-161">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="0f43d-161">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="0f43d-162">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-162">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="0f43d-163">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f43d-163">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0f43d-164">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="0f43d-164">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="0f43d-165">PowerShell の書式設定およびファイルの種類の作成</span><span class="sxs-lookup"><span data-stu-id="0f43d-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
