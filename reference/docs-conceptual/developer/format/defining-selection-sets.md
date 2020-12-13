---
ms.date: 09/13/2016
ms.topic: reference
title: 選択セットを定義する
description: 選択セットを定義する
ms.openlocfilehash: d709a368a45623d56fdbf4e98a11a5e5f8a193fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648260"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="42e51-103">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="42e51-103">Defining Selection Sets</span></span>

<span data-ttu-id="42e51-104">複数のビューおよびコントロールを作成する場合は、選択セットと呼ばれるオブジェクトのセットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42e51-104">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="42e51-105">選択セットを使用すると、各ビューまたはコントロールに対して個別に定義しなくても、オブジェクトを一度定義することができます。</span><span class="sxs-lookup"><span data-stu-id="42e51-105">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="42e51-106">通常、選択セットは、関連する一連の .NET オブジェクトがある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="42e51-106">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="42e51-107">たとえば、 `FileSystem` 書式設定ファイル (FileSystem.format.ps1xml) では、複数のビューで使用するファイルシステムの種類の選択セットが定義されています。</span><span class="sxs-lookup"><span data-stu-id="42e51-107">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="42e51-108">選択セットが定義され参照されている場所</span><span class="sxs-lookup"><span data-stu-id="42e51-108">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="42e51-109">選択セットは、書式設定ファイルで定義されているすべてのビューとコントロールで使用できる共通データの一部として定義します。</span><span class="sxs-lookup"><span data-stu-id="42e51-109">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="42e51-110">次の例では、3つの選択セットを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42e51-110">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="42e51-111">選択セットは、次の方法で参照できます。</span><span class="sxs-lookup"><span data-stu-id="42e51-111">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="42e51-112">各ビューには `ViewSelectedBy` 、ビューを使用して表示されるオブジェクトを定義する要素があります。</span><span class="sxs-lookup"><span data-stu-id="42e51-112">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="42e51-113">`ViewSelectedBy`要素には、 `SelectionSetName` ビューのすべての定義で使用される選択セットを指定する子要素があります。</span><span class="sxs-lookup"><span data-stu-id="42e51-113">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="42e51-114">ビューから参照できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="42e51-114">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="42e51-115">ビューまたはコントロールの各定義では、 `EntrySelectedBy` 要素によって、その定義を使用して表示されるオブジェクトが定義されます。</span><span class="sxs-lookup"><span data-stu-id="42e51-115">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="42e51-116">通常、ビューまたはコントロールには定義が1つしかないため、オブジェクトは要素によって定義され `ViewSelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="42e51-116">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="42e51-117">`EntrySelectedBy`定義の要素には、 `SelectionSetName` 選択セットを指定する子要素があります。</span><span class="sxs-lookup"><span data-stu-id="42e51-117">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="42e51-118">定義の選択セットを指定する場合、要素の他の子要素を指定することはできません `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="42e51-118">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="42e51-119">ビューまたはコントロールの各定義では、要素を使用して、 `SelectionCondition` 定義を使用するときの条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="42e51-119">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="42e51-120">`SelectionCondition`要素には、 `SelectionSetName` 条件をトリガーする選択セットを指定する子要素があります。</span><span class="sxs-lookup"><span data-stu-id="42e51-120">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="42e51-121">この条件は、選択セットで定義されたオブジェクトのいずれかが表示されたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="42e51-121">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="42e51-122">これらの条件を設定する方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e51-122">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="42e51-123">選択セットの例</span><span class="sxs-lookup"><span data-stu-id="42e51-123">Selection Set Example</span></span>

<span data-ttu-id="42e51-124">次の例は、Windows PowerShell によって提供される書式設定ファイルから直接取得される選択セットを示して `FileSystem` います。</span><span class="sxs-lookup"><span data-stu-id="42e51-124">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="42e51-125">その他の Windows PowerShell フォーマットファイルの詳細については、「 [Windows powershell の書式設定ファイル](./powershell-formatting-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e51-125">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

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

<span data-ttu-id="42e51-126">前の選択セットは、 `ViewSelectedBy` テーブルビューの要素で参照されます。</span><span class="sxs-lookup"><span data-stu-id="42e51-126">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

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

## <a name="xml-elements"></a><span data-ttu-id="42e51-127">XML 要素</span><span class="sxs-lookup"><span data-stu-id="42e51-127">XML Elements</span></span>

 <span data-ttu-id="42e51-128">定義できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="42e51-128">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="42e51-129">次の XML 要素を使用して、選択セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="42e51-129">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="42e51-130">[Selectionsets](./selectionsets-element-format.md)要素は、書式設定ファイルのビューおよびコントロールによって参照される .net オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="42e51-130">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="42e51-131">[Selectionset](./selectionset-element-format.md)要素は、.net オブジェクトの1つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="42e51-131">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="42e51-132">[Name](./name-element-for-selectionset-format.md)要素は、選択セットを参照するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-132">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="42e51-133">[Types](./types-element-for-selectionset-format.md)要素は、選択セットのオブジェクトの .net 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-133">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="42e51-134">(書式設定ファイル内では、オブジェクトは .NET 型によって指定されます)。</span><span class="sxs-lookup"><span data-stu-id="42e51-134">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="42e51-135">次の XML 要素を使用して、選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-135">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="42e51-136">次の要素は、ビューのすべての定義で使用する選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-136">The following element specifies the selection set to use in all the definitions of the view:</span></span>

  - [<span data-ttu-id="42e51-137">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-137">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

  - [<span data-ttu-id="42e51-138">GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-138">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="42e51-139">次の要素は、1つのビュー定義で使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-139">The following elements specify the selection set used by a single view definition:</span></span>

  - [<span data-ttu-id="42e51-140">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="42e51-141">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-141">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="42e51-142">WideControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-142">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="42e51-143">View の CustomControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-143">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="42e51-144">次の要素は、コモンコントロール定義と view コントロール定義で使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-144">The following elements specify the selection set used by common and view control definitions:</span></span>

  - [<span data-ttu-id="42e51-145">View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-145">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [<span data-ttu-id="42e51-146">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-146">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="42e51-147">次の要素では、拡張するオブジェクトを定義するときに使用する選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-147">The following elements specify the selection set used when you define which object to expand:</span></span>

  - [<span data-ttu-id="42e51-148">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-148">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="42e51-149">次の要素は、選択条件で使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="42e51-149">The following elements specify the selection set used by selection conditions.</span></span>

  - [<span data-ttu-id="42e51-150">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-150">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="42e51-151">View の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-151">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [<span data-ttu-id="42e51-152">View の CustomControl の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-152">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [<span data-ttu-id="42e51-153">EnumerableExpansion の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [<span data-ttu-id="42e51-154">ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [<span data-ttu-id="42e51-155">TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="42e51-156">WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-156">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [<span data-ttu-id="42e51-157">GroupBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42e51-157">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="42e51-158">参照</span><span class="sxs-lookup"><span data-stu-id="42e51-158">See Also</span></span>

[<span data-ttu-id="42e51-159">SelectionSets</span><span class="sxs-lookup"><span data-stu-id="42e51-159">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="42e51-160">SelectionSet</span><span class="sxs-lookup"><span data-stu-id="42e51-160">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="42e51-161">名前</span><span class="sxs-lookup"><span data-stu-id="42e51-161">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="42e51-162">型</span><span class="sxs-lookup"><span data-stu-id="42e51-162">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="42e51-163">PowerShell 書式設定ファイル</span><span class="sxs-lookup"><span data-stu-id="42e51-163">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="42e51-164">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="42e51-164">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="42e51-165">PowerShell の形式と種類のファイルの作成</span><span class="sxs-lookup"><span data-stu-id="42e51-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
