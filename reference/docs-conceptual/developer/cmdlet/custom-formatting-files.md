---
ms.date: 09/13/2016
ms.topic: reference
title: ファイルにカスタム書式設定を適用する
description: ファイルにカスタム書式設定を適用する
ms.openlocfilehash: 16e1c1046e25b35ff346585a5fd930c449c04bf8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653247"
---
# <a name="custom-formatting-files"></a><span data-ttu-id="cc3d6-103">ファイルにカスタム書式設定を適用する</span><span class="sxs-lookup"><span data-stu-id="cc3d6-103">Custom Formatting Files</span></span>

<span data-ttu-id="cc3d6-104">コマンドレット、関数、およびスクリプトによって返されるオブジェクトの表示形式は、書式設定ファイル (format.ps1xml ファイル) を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-104">The display format for the objects returned by cmdlets, functions, and scripts are defined using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="cc3d6-105">これらのファイルのいくつかは、windows powershell コマンドレットによって返されるオブジェクトの既定の表示形式を定義するために、Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-105">Several of these files are provided by Windows PowerShell to define the default display format for those objects returned by Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cc3d6-106">ただし、独自のカスタム書式設定ファイルを作成して、既定の表示形式を上書きしたり、独自のコマンドによって返されるオブジェクトの表示を定義したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-106">However, you can also create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

<span data-ttu-id="cc3d6-107">Windows PowerShell は、これらの書式設定ファイルのデータを使用して、表示される内容と、データの書式設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-107">Windows PowerShell uses the data in these formatting files to determine what is displayed and how the data is formatted.</span></span> <span data-ttu-id="cc3d6-108">表示されるデータには、オブジェクトのプロパティまたはスクリプトブロックの値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-108">The displayed data can include the properties of an object or the value of a script block.</span></span>  <span data-ttu-id="cc3d6-109">スクリプトブロックは、オブジェクトのプロパティから直接使用できない値を表示する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-109">Script blocks are used if you want to display some value that is not available directly from the properties of an object.</span></span> <span data-ttu-id="cc3d6-110">たとえば、オブジェクトの2つのプロパティの値を加算し、その合計を個別のデータとして表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-110">For example, you may want to add the value of two properties of an object and display the sum as a separate piece of data.</span></span> <span data-ttu-id="cc3d6-111">独自の書式設定ファイルを作成する場合は、表示するオブジェクトの *ビュー* を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-111">When you write your own formatting file, you will need to define *views* for the objects that you want to display.</span></span> <span data-ttu-id="cc3d6-112">各オブジェクトに対して1つのビューを定義したり、複数のオブジェクトに対して1つのビューを定義したり、同じオブジェクトに対して複数のビューを定義したりできます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-112">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="cc3d6-113">定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-113">There is no limit to the number of views that you can define.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc3d6-114">書式設定ファイルでは、パイプラインに返されるオブジェクトの要素は決定されません。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-114">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="cc3d6-115">オブジェクトがパイプラインに返されると、そのオブジェクトのすべてのメンバーが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-115">When an object is returned to the pipeline, all members of that object are available.</span></span>

## <a name="format-views"></a><span data-ttu-id="cc3d6-116">ビューの書式設定</span><span class="sxs-lookup"><span data-stu-id="cc3d6-116">Format Views</span></span>

<span data-ttu-id="cc3d6-117">書式設定ビューでは、テーブル形式、リスト形式、ワイド形式、およびカスタム書式でオブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-117">Formatting views can display objects in a table format, a list format, a wide format, and a custom format.</span></span> <span data-ttu-id="cc3d6-118">ほとんどの場合、各書式設定定義は、ビューを記述する XML タグのセットによって記述されます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-118">For the most part, each formatting definition is described by a set of XML tags that describe a view.</span></span> <span data-ttu-id="cc3d6-119">各ビューには、ビューの名前、ビューを使用するオブジェクト、およびテーブルビューの列と行の情報など、ビューの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-119">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="cc3d6-120">次のビューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-120">The following views are available.</span></span>

<span data-ttu-id="cc3d6-121">テーブルビューには、1つまたは複数の列にオブジェクトまたはスクリプトブロックの値のプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-121">Table view Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="cc3d6-122">各列は、オブジェクトのプロパティまたはスクリプトブロック値を表します。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-122">Each column represents a property of the object or a script block value.</span></span> <span data-ttu-id="cc3d6-123">オブジェクトのすべてのプロパティ、オブジェクトのプロパティのサブセット、またはプロパティとスクリプトブロック値の組み合わせを表示するテーブルビューを定義できます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-123">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script block values.</span></span> <span data-ttu-id="cc3d6-124">テーブルの各行は、返されたオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-124">Each row of the table represents a returned object.</span></span> <span data-ttu-id="cc3d6-125">このビューの詳細については、「 [テーブルビュー](../format/creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-125">For more information about this view, see [Table View](../format/creating-a-table-view.md).</span></span>

<span data-ttu-id="cc3d6-126">リストビューには、1つの列にオブジェクトまたはスクリプトブロックの値のプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-126">List view Lists the properties of an object or a script block value in a single column.</span></span> <span data-ttu-id="cc3d6-127">一覧の各行には、省略可能なラベルまたはプロパティ名の後にプロパティまたはスクリプトブロックの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-127">Each row of the list displays an optional label or the property name followed by the value of the property or script block.</span></span> <span data-ttu-id="cc3d6-128">このビューの詳細については、「 [リストビュー](../format/creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-128">For more information about this view, see [List View](../format/creating-a-list-view.md).</span></span>

<span data-ttu-id="cc3d6-129">ワイドビュー1つまたは複数の列にオブジェクトまたはスクリプトブロックの値の1つのプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-129">Wide view Lists a single property of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="cc3d6-130">このビューにはラベルまたはヘッダーがありません。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-130">There is no label or header for this view.</span></span> <span data-ttu-id="cc3d6-131">このビューの詳細については、「 [Wide ビュー](../format/creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-131">For more information about this view, see [Wide View](../format/creating-a-wide-view.md).</span></span>

<span data-ttu-id="cc3d6-132">カスタムビューでは、テーブルビュー、リストビュー、またはワイドビューの固定構造に準拠していないオブジェクトプロパティまたはスクリプトブロック値のカスタマイズ可能なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-132">Custom view Displays a customizable view of object properties or script block values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="cc3d6-133">スタンドアロンのカスタムビューを定義することも、テーブルビューやリストビューなどの別のビューで使用されるカスタムビューを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-133">You can define a standalone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="cc3d6-134">このビューの詳細については、「 [カスタムビュー](../format/creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-134">For more information about this view, see [Custom View](../format/creating-custom-controls.md).</span></span>

## <a name="view-xml-elements"></a><span data-ttu-id="cc3d6-135">XML 要素の表示</span><span class="sxs-lookup"><span data-stu-id="cc3d6-135">View XML Elements</span></span>

<span data-ttu-id="cc3d6-136">次の例は、2つの列を含むテーブルビューを定義するために使用される XML タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-136">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="cc3d6-137">[Viewdefinitions](../format/viewdefinitions-element-format.md)要素は、書式設定ファイルで定義されているすべてのビューのコンテナー要素です。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-137">The [ViewDefinitions](../format/viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="cc3d6-138">[View](../format/view-element-format.md)要素は、特定のテーブル、リスト、ワイド、またはカスタムビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-138">The [View](../format/view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="cc3d6-139">各ビュー内では、 [name](../format/name-element-for-view-format.md) 要素はビューの名前を指定し、 [viewselectedby](../format/viewselectedby-element-format.md) 要素はビューを使用するオブジェクトを定義し、さまざまなコントロール要素 ( `TableControl` 要素など) がビューの形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="cc3d6-139">Within each view, the [Name](../format/name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](../format/viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element) define the format of the view.</span></span>

```xml
ViewDefinitions
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

## <a name="see-also"></a><span data-ttu-id="cc3d6-140">参照</span><span class="sxs-lookup"><span data-stu-id="cc3d6-140">See Also</span></span>

[<span data-ttu-id="cc3d6-141">テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="cc3d6-141">Table View</span></span>](../format/creating-a-table-view.md)

[<span data-ttu-id="cc3d6-142">リストビュー</span><span class="sxs-lookup"><span data-stu-id="cc3d6-142">List View</span></span>](../format/creating-a-list-view.md)

[<span data-ttu-id="cc3d6-143">ワイドビュー</span><span class="sxs-lookup"><span data-stu-id="cc3d6-143">Wide View</span></span>](../format/creating-a-wide-view.md)

[<span data-ttu-id="cc3d6-144">カスタムビュー</span><span class="sxs-lookup"><span data-stu-id="cc3d6-144">Custom View</span></span>](../format/creating-custom-controls.md)

[<span data-ttu-id="cc3d6-145">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="cc3d6-145">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
