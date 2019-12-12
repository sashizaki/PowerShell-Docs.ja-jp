---
title: 選択セットの定義 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368851"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="3b15d-102">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="3b15d-102">Defining Selection Sets</span></span>

<span data-ttu-id="3b15d-103">複数のビューおよびコントロールを作成する場合は、選択セットと呼ばれるオブジェクトのセットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-103">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="3b15d-104">選択セットを使用すると、各ビューまたはコントロールに対して個別に定義しなくても、オブジェクトを一度定義することができます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-104">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="3b15d-105">通常、選択セットは、関連する一連の .NET オブジェクトがある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-105">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="3b15d-106">たとえば、`FileSystem` の書式設定ファイル (types.ps1xml) では、複数のビューが使用するファイルシステムの種類の選択セットが定義されています。</span><span class="sxs-lookup"><span data-stu-id="3b15d-106">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="3b15d-107">選択セットが定義され参照されている場所</span><span class="sxs-lookup"><span data-stu-id="3b15d-107">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="3b15d-108">選択セットは、書式設定ファイルで定義されているすべてのビューとコントロールで使用できる共通データの一部として定義します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-108">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="3b15d-109">次の例では、3つの選択セットを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-109">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="3b15d-110">選択セットは、次の方法で参照できます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-110">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="3b15d-111">各ビューには、ビューを使用して表示されるオブジェクトを定義する `ViewSelectedBy` 要素があります。</span><span class="sxs-lookup"><span data-stu-id="3b15d-111">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="3b15d-112">`ViewSelectedBy` 要素には、ビューのすべての定義で使用する選択セットを指定する `SelectionSetName` 子要素があります。</span><span class="sxs-lookup"><span data-stu-id="3b15d-112">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="3b15d-113">ビューから参照できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3b15d-113">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="3b15d-114">ビューまたはコントロールの各定義では、`EntrySelectedBy` 要素によって、その定義を使用して表示されるオブジェクトが定義されます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-114">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="3b15d-115">通常、ビューまたはコントロールには定義が1つだけ存在するので、オブジェクトは `ViewSelectedBy` 要素によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-115">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="3b15d-116">定義の `EntrySelectedBy` 要素には、選択セットを指定する `SelectionSetName` 子要素があります。</span><span class="sxs-lookup"><span data-stu-id="3b15d-116">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="3b15d-117">定義の選択セットを指定する場合は、`EntrySelectedBy` 要素の他の子要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b15d-117">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="3b15d-118">ビューまたはコントロールの各定義では、`SelectionCondition` 要素を使用して、定義を使用するときの条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-118">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="3b15d-119">`SelectionCondition` 要素には、条件をトリガーする選択セットを指定する `SelectionSetName` 子要素があります。</span><span class="sxs-lookup"><span data-stu-id="3b15d-119">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="3b15d-120">この条件は、選択セットで定義されたオブジェクトのいずれかが表示されたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-120">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="3b15d-121">これらの条件を設定する方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b15d-121">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="3b15d-122">選択セットの例</span><span class="sxs-lookup"><span data-stu-id="3b15d-122">Selection Set Example</span></span>

<span data-ttu-id="3b15d-123">次の例は、Windows PowerShell によって提供される `FileSystem` フォーマットファイルから直接取得される選択セットを示しています。</span><span class="sxs-lookup"><span data-stu-id="3b15d-123">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="3b15d-124">その他の Windows PowerShell フォーマットファイルの詳細については、「 [Windows powershell の書式設定ファイル](./powershell-formatting-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b15d-124">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

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

<span data-ttu-id="3b15d-125">前の選択セットは、テーブルビューの `ViewSelectedBy` 要素で参照されます。</span><span class="sxs-lookup"><span data-stu-id="3b15d-125">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

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

## <a name="xml-elements"></a><span data-ttu-id="3b15d-126">XML 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-126">XML Elements</span></span>

 <span data-ttu-id="3b15d-127">定義できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3b15d-127">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="3b15d-128">次の XML 要素を使用して、選択セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-128">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="3b15d-129">[Selectionsets](./selectionsets-element-format.md)要素は、書式設定ファイルのビューおよびコントロールによって参照される .net オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-129">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="3b15d-130">[Selectionset](./selectionset-element-format.md)要素は、.net オブジェクトの1つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-130">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="3b15d-131">[Name](./name-element-for-selectionset-format.md)要素は、選択セットを参照するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-131">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="3b15d-132">[Types](./types-element-for-selectionset-format.md)要素は、選択セットのオブジェクトの .net 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-132">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="3b15d-133">(書式設定ファイル内では、オブジェクトは .NET 型によって指定されます)。</span><span class="sxs-lookup"><span data-stu-id="3b15d-133">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="3b15d-134">次の XML 要素を使用して、選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-134">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="3b15d-135">次の要素は、ビューのすべての定義で使用する選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-135">The following element specifies the selection set to use in all the definitions of the view:</span></span>

    - [<span data-ttu-id="3b15d-136">ViewSelectedBy (Format) の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-136">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

    - [<span data-ttu-id="3b15d-137">GroupBy (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-137">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="3b15d-138">次の要素は、1つのビュー定義で使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-138">The following elements specify the selection set used by a single view definition:</span></span>

    - [<span data-ttu-id="3b15d-139">ListControl (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-139">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [<span data-ttu-id="3b15d-140">TableControl (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-140">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="3b15d-141">WideControl (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-141">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [<span data-ttu-id="3b15d-142">CustomControl for View (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-142">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="3b15d-143">次の要素は、コモンコントロール定義と view コントロール定義で使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-143">The following elements specify the selection set used by common and view control definitions:</span></span>

    - [<span data-ttu-id="3b15d-144">ビューのコントロール (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-144">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [<span data-ttu-id="3b15d-145">構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-145">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="3b15d-146">次の要素では、拡張するオブジェクトを定義するときに使用する選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-146">The following elements specify the selection set used when you define which object to expand:</span></span>

    - [<span data-ttu-id="3b15d-147">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-147">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="3b15d-148">次の要素は、選択条件で使用される選択セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b15d-148">The following elements specify the selection set used by selection conditions.</span></span>

    - [<span data-ttu-id="3b15d-149">構成用のコントロールの SelectionCondition の SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="3b15d-149">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="3b15d-150">ビューのコントロール (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-150">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [<span data-ttu-id="3b15d-151">View (Format) の CustomControl の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-151">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [<span data-ttu-id="3b15d-152">列挙 Able膨張 (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-152">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [<span data-ttu-id="3b15d-153">EntrySelectedBy for ListEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [<span data-ttu-id="3b15d-154">TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="3b15d-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="3b15d-155">EntrySelectedBy for WideEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [<span data-ttu-id="3b15d-156">GroupBy (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3b15d-156">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="3b15d-157">参照</span><span class="sxs-lookup"><span data-stu-id="3b15d-157">See Also</span></span>

[<span data-ttu-id="3b15d-158">SelectionSets</span><span class="sxs-lookup"><span data-stu-id="3b15d-158">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="3b15d-159">SelectionSet</span><span class="sxs-lookup"><span data-stu-id="3b15d-159">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="3b15d-160">名前</span><span class="sxs-lookup"><span data-stu-id="3b15d-160">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="3b15d-161">型</span><span class="sxs-lookup"><span data-stu-id="3b15d-161">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="3b15d-162">PowerShell のフォーマットファイル</span><span class="sxs-lookup"><span data-stu-id="3b15d-162">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="3b15d-163">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="3b15d-163">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="3b15d-164">PowerShell の形式と種類のファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3b15d-164">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
