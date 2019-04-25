---
title: 選択範囲のセットを定義する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066313"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="07aca-102">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="07aca-102">Defining Selection Sets</span></span>

<span data-ttu-id="07aca-103">複数のビューとコントロールを作成する場合は、選択範囲のセットとして参照されるオブジェクトのセットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="07aca-103">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="07aca-104">選択範囲のセットでは、各ビューまたはコントロールの繰り返しに定義することがなく 1 回、オブジェクトを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="07aca-104">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="07aca-105">通常、選択範囲のセットは、関連する .NET オブジェクトのセットがある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="07aca-105">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="07aca-106">たとえば、`FileSystem`書式設定ファイル (FileSystem.format.ps1xml) がいくつかのビューを使用して、ファイル システムの種類の選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="07aca-106">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="07aca-107">選択範囲のセットが定義および参照を</span><span class="sxs-lookup"><span data-stu-id="07aca-107">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="07aca-108">すべてのビューと書式設定ファイルで定義されているコントロールで使用できる一般的なデータの一部としては、選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="07aca-108">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="07aca-109">次の例では、次の 3 つの選択範囲のセットを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="07aca-109">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="07aca-110">選択範囲を参照する次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-110">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="07aca-111">各ビューでは、`ViewSelectedBy`ビューを使用して表示されるオブジェクトを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="07aca-111">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="07aca-112">`ViewSelectedBy`要素には、`SelectionSetName`選択範囲を指定する子要素がビューの使用のすべての定義を設定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-112">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="07aca-113">ビューから参照できるように選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="07aca-113">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="07aca-114">ビューまたはコントロールの各定義における、`EntrySelectedBy`要素は、その定義を使用して表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="07aca-114">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="07aca-115">通常、ビューまたはコントロールに 1 つだけ定義して、オブジェクトが定義されているため、`ViewSelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="07aca-115">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="07aca-116">`EntrySelectedBy`定義の要素には、`SelectionSetName`選択範囲のセットを指定する子要素。</span><span class="sxs-lookup"><span data-stu-id="07aca-116">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="07aca-117">選択の定義のセットを指定する場合の他の子要素のいずれかを指定できません、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="07aca-117">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="07aca-118">ビューまたはコントロールの各定義における、`SelectionCondition`定義を使用する場合の条件を指定する要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="07aca-118">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="07aca-119">`SelectionCondition`要素には、`SelectionSetName`選択範囲のセットを示す子要素が条件をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="07aca-119">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="07aca-120">選択範囲のセットで定義されたオブジェクトのいずれかが表示される場合は、条件がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="07aca-120">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="07aca-121">これらの条件を設定する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="07aca-121">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="07aca-122">選択範囲のセットの例</span><span class="sxs-lookup"><span data-stu-id="07aca-122">Selection Set Example</span></span>

<span data-ttu-id="07aca-123">次の例では、選択セットから直接実行する、 `FileSystem` Windows PowerShell によって提供されるファイルの書式設定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-123">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="07aca-124">その他の Windows PowerShell の書式設定ファイルの詳細については、次を参照してください。 [Windows PowerShell の書式設定ファイル](./powershell-formatting-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="07aca-124">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

<span data-ttu-id="07aca-125">前の選択範囲のセットが参照されている、`ViewSelectedBy`テーブル ビューの要素。</span><span class="sxs-lookup"><span data-stu-id="07aca-125">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a><span data-ttu-id="07aca-126">XML 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-126">XML Elements</span></span>

 <span data-ttu-id="07aca-127">定義できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="07aca-127">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="07aca-128">次の XML 要素を使用して、選択範囲のセットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="07aca-128">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="07aca-129">[SelectionSets](./selectionsets-element-format.md)ビューによって参照されている .NET オブジェクトのセットと書式設定ファイルのコントロール要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="07aca-129">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="07aca-130">[SelectionSet](./selectionset-element-format.md)要素は、.NET オブジェクトの 1 つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="07aca-130">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="07aca-131">[名前](./name-element-for-selectionset-format.md)要素は、選択範囲のセットを参照するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-131">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="07aca-132">[型](./types-element-for-selectionset-format.md)要素は、選択範囲のセットのオブジェクトの .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-132">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="07aca-133">(ファイルの書式設定、内でオブジェクトが指定されてをその .NET 型です。)</span><span class="sxs-lookup"><span data-stu-id="07aca-133">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="07aca-134">次の XML 要素を使用して、選択範囲のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-134">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="07aca-135">次の要素は、ビューのすべての定義で使用する設定の選択範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-135">The following element specifies the selection set to use in all the definitions of the view:</span></span>

    - [<span data-ttu-id="07aca-136">ViewSelectedBy (形式) の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-136">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

    - [<span data-ttu-id="07aca-137">GroupBy (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-137">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="07aca-138">次の要素は、1 つのビュー定義で使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-138">The following elements specify the selection set used by a single view definition:</span></span>

    - [<span data-ttu-id="07aca-139">ListControl (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-139">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [<span data-ttu-id="07aca-140">TableControl (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-140">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="07aca-141">WideControl (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-141">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [<span data-ttu-id="07aca-142">ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-142">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="07aca-143">次の要素が共通で使用される選択範囲のセットを指定し、コントロールの定義を表示します。</span><span class="sxs-lookup"><span data-stu-id="07aca-143">The following elements specify the selection set used by common and view control definitions:</span></span>

    - [<span data-ttu-id="07aca-144">コントロールが表示されます (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-144">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [<span data-ttu-id="07aca-145">構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-145">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="07aca-146">次の要素を展開するには、どのオブジェクトを定義するときに使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-146">The following elements specify the selection set used when you define which object to expand:</span></span>

    - [<span data-ttu-id="07aca-147">EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-147">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="07aca-148">次の要素は、選択条件で使用される選択範囲のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="07aca-148">The following elements specify the selection set used by selection conditions.</span></span>

    - [<span data-ttu-id="07aca-149">構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-149">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="07aca-150">コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-150">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [<span data-ttu-id="07aca-151">ビュー (形式) のカスタム コントロールの SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-151">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [<span data-ttu-id="07aca-152">EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-152">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [<span data-ttu-id="07aca-153">EntrySelectedBy ListEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [<span data-ttu-id="07aca-154">TableControl (形式) の EntrySelectedBy の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="07aca-155">EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [<span data-ttu-id="07aca-156">GroupBy (形式) の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="07aca-156">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="07aca-157">参照</span><span class="sxs-lookup"><span data-stu-id="07aca-157">See Also</span></span>

[<span data-ttu-id="07aca-158">SelectionSets</span><span class="sxs-lookup"><span data-stu-id="07aca-158">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="07aca-159">SelectionSet</span><span class="sxs-lookup"><span data-stu-id="07aca-159">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="07aca-160">名前</span><span class="sxs-lookup"><span data-stu-id="07aca-160">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="07aca-161">型</span><span class="sxs-lookup"><span data-stu-id="07aca-161">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="07aca-162">PowerShell の書式設定ファイル</span><span class="sxs-lookup"><span data-stu-id="07aca-162">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="07aca-163">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="07aca-163">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="07aca-164">PowerShell の書式設定およびファイルの種類の作成</span><span class="sxs-lookup"><span data-stu-id="07aca-164">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
