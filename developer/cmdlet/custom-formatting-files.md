---
title: カスタム ファイルを書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85d27545-8097-4010-9947-6d8b3ce2eac0
caps.latest.revision: 15
ms.openlocfilehash: 71c1c181058c5646c817b90d9832976a78c6c7de
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860608"
---
# <a name="custom-formatting-files"></a><span data-ttu-id="a7854-102">ファイルにカスタム書式設定を適用する</span><span class="sxs-lookup"><span data-stu-id="a7854-102">Custom Formatting Files</span></span>

<span data-ttu-id="a7854-103">コマンドレット、関数、およびスクリプトによって返されるオブジェクトの表示形式は、書式設定ファイル (format.ps1xml ファイル) を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="a7854-103">The display format for the objects returned by cmdlets, functions, and scripts are defined using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="a7854-104">これらのファイルのいくつかは、Windows PowerShell コマンドレットによって返されるこれらのオブジェクトの既定の表示形式を定義する Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="a7854-104">Several of these files are provided by Windows PowerShell to define the default display format for those objects returned by Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a7854-105">ただし、カスタムの書式設定ファイルの既定の表示形式を上書きするか、独自のコマンドによって返されるオブジェクトの表示を定義するは、自分を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7854-105">However, you can also create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

<span data-ttu-id="a7854-106">Windows PowerShell では、これらの書式設定ファイルでデータを使用して、表示される内容と、データの書式設定方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="a7854-106">Windows PowerShell uses the data in these formatting files to determine what is displayed and how the data is formatted.</span></span> <span data-ttu-id="a7854-107">表示されるデータには、スクリプト ブロックの値またはオブジェクトのプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a7854-107">The displayed data can include the properties of an object or the value of a script block.</span></span>  <span data-ttu-id="a7854-108">スクリプト ブロックは、オブジェクトのプロパティから直接は使用できないいくつかの値を表示する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7854-108">Script blocks are used if you want to display some value that is not available directly from the properties of an object.</span></span> <span data-ttu-id="a7854-109">たとえば、オブジェクトの 2 つのプロパティの値を追加し、別のデータとして合計を表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="a7854-109">For example, you may want to add the value of two properties of an object and display the sum as a separate piece of data.</span></span> <span data-ttu-id="a7854-110">独自の書式設定ファイルを作成するときに、定義する必要があります。*ビュー*を表示するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a7854-110">When you write your own formatting file, you will need to define *views* for the objects that you want to display.</span></span> <span data-ttu-id="a7854-111">オブジェクトごとに 1 つのビューを定義することができます、複数のオブジェクトの 1 つのビューを定義することができます、または同じオブジェクトに対して複数のビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a7854-111">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="a7854-112">定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="a7854-112">There is no limit to the number of views that you can define.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7854-113">書式設定ファイルは、パイプラインに返されるオブジェクトの要素を特定できません。</span><span class="sxs-lookup"><span data-stu-id="a7854-113">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="a7854-114">パイプラインにオブジェクトが返されると、そのオブジェクトのすべてのメンバーは使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7854-114">When an object is returned to the pipeline, all members of that object are available.</span></span>

## <a name="format-views"></a><span data-ttu-id="a7854-115">形式のビュー</span><span class="sxs-lookup"><span data-stu-id="a7854-115">Format Views</span></span>

<span data-ttu-id="a7854-116">書式設定のビューは、表形式や一覧形式、ワイド形式では、カスタム書式指定オブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a7854-116">Formatting views can display objects in a table format, a list format, a wide format, and a custom format.</span></span> <span data-ttu-id="a7854-117">ほとんどの場合、各書式設定の定義は、一連のビューを記述する XML タグで表されます。</span><span class="sxs-lookup"><span data-stu-id="a7854-117">For the most part, each formatting definition is described by a set of XML tags that describe a view.</span></span> <span data-ttu-id="a7854-118">それぞれのビューには、ビュー、およびテーブル ビューの列と行情報など、ビューの要素を使用するオブジェクトには、ビューの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7854-118">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="a7854-119">次のビューは使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7854-119">The following views are available.</span></span>

<span data-ttu-id="a7854-120">テーブル ビューには、オブジェクトまたはスクリプト ブロックの値を 1 つまたは複数の列のプロパティが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a7854-120">Table view Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="a7854-121">各列は、オブジェクトまたはスクリプト ブロックの値のプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="a7854-121">Each column represents a property of the object or a script block value.</span></span> <span data-ttu-id="a7854-122">オブジェクト、オブジェクト、またはプロパティとスクリプト ブロックの値の組み合わせのプロパティのサブセットのすべてのプロパティを表示するテーブルのビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a7854-122">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script block values.</span></span> <span data-ttu-id="a7854-123">テーブルの各行は、返されたオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="a7854-123">Each row of the table represents a returned object.</span></span> <span data-ttu-id="a7854-124">このビューの詳細については、次を参照してください。[テーブル ビュー](../format/creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7854-124">For more information about this view, see [Table View](../format/creating-a-table-view.md).</span></span>

<span data-ttu-id="a7854-125">リスト ビューには、オブジェクトまたはスクリプト ブロックの値を 1 つの列のプロパティが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a7854-125">List view Lists the properties of an object or a script block value in a single column.</span></span> <span data-ttu-id="a7854-126">リストの各行には、オプションのラベルまたはプロパティ名の後に、プロパティまたはスクリプト ブロックの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7854-126">Each row of the list displays an optional label or the property name followed by the value of the property or script block.</span></span> <span data-ttu-id="a7854-127">このビューの詳細については、次を参照してください。[リスト ビュー](../format/creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7854-127">For more information about this view, see [List View](../format/creating-a-list-view.md).</span></span>

<span data-ttu-id="a7854-128">表示幅が広いでは、オブジェクトまたはスクリプト ブロックの値を 1 つまたは複数の列内の 1 つのプロパティが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a7854-128">Wide view Lists a single property of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="a7854-129">ラベルまたはこのビューのヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="a7854-129">There is no label or header for this view.</span></span> <span data-ttu-id="a7854-130">このビューの詳細については、次を参照してください。[表示幅が広い](../format/creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7854-130">For more information about this view, see [Wide View](../format/creating-a-wide-view.md).</span></span>

<span data-ttu-id="a7854-131">カスタム ビューには、テーブルのビュー、リスト ビュー、またはワイド ビューの厳格な構造に準拠していないオブジェクトのプロパティまたはスクリプト ブロックの値のカスタマイズ可能なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7854-131">Custom view Displays a customizable view of object properties or script block values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="a7854-132">スタンドアロンのカスタム ビューを定義するまたはテーブル ビューまたはリスト ビューなどの別のビューで使用されるカスタム ビューを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a7854-132">You can define a standalone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="a7854-133">このビューの詳細については、次を参照してください。[カスタム ビュー](../format/creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7854-133">For more information about this view, see [Custom View](../format/creating-custom-controls.md).</span></span>

## <a name="view-xml-elements"></a><span data-ttu-id="a7854-134">ビューの XML 要素</span><span class="sxs-lookup"><span data-stu-id="a7854-134">View XML Elements</span></span>

<span data-ttu-id="a7854-135">次の例は、2 つの列を含むテーブルのビューを定義するために使用する XML タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7854-135">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="a7854-136">[ViewDefinitions](../format/viewdefinitions-element-format.md)要素が書式設定ファイルで定義されているすべてのビューのコンテナー要素。</span><span class="sxs-lookup"><span data-stu-id="a7854-136">The [ViewDefinitions](../format/viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="a7854-137">[ビュー](../format/view-element-format.md)要素は、特定のテーブル、リスト、ビュー、またはカスタム ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="a7854-137">The [View](../format/view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="a7854-138">それぞれのビュー内で、[名前](../format/name-element-for-view-format.md)要素は、ビューの名前を指定します、 [ViewSelectedBy](../format/viewselectedby-element-format.md)要素は、ビュー、および別のコントロール要素を使用するオブジェクトを定義します (など、 `TableControl`要素) の表示形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="a7854-138">Within each view, the [Name](../format/name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](../format/viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element) define the format of the view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a7854-139">参照</span><span class="sxs-lookup"><span data-stu-id="a7854-139">See Also</span></span>

[<span data-ttu-id="a7854-140">テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="a7854-140">Table View</span></span>](../format/creating-a-table-view.md)

[<span data-ttu-id="a7854-141">リスト ビュー</span><span class="sxs-lookup"><span data-stu-id="a7854-141">List View</span></span>](../format/creating-a-list-view.md)

[<span data-ttu-id="a7854-142">表示幅が広い</span><span class="sxs-lookup"><span data-stu-id="a7854-142">Wide View</span></span>](../format/creating-a-wide-view.md)

[<span data-ttu-id="a7854-143">カスタム ビュー</span><span class="sxs-lookup"><span data-stu-id="a7854-143">Custom View</span></span>](../format/creating-custom-controls.md)

[<span data-ttu-id="a7854-144">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="a7854-144">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
