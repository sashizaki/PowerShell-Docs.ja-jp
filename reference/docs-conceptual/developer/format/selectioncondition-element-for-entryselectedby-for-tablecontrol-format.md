---
title: TableControl (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368391"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="67970-102">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="67970-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="67970-103">テーブルビューのこの定義に使用する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="67970-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="67970-104">テーブル定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="67970-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="67970-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の要素TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="67970-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="67970-106">構文</span><span class="sxs-lookup"><span data-stu-id="67970-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="67970-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="67970-107">Attributes and Elements</span></span>

<span data-ttu-id="67970-108">次のセクションでは、属性、子要素、および SelectionCondition 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="67970-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="67970-109">属性</span><span class="sxs-lookup"><span data-stu-id="67970-109">Attributes</span></span>

<span data-ttu-id="67970-110">なし。</span><span class="sxs-lookup"><span data-stu-id="67970-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="67970-111">子要素</span><span class="sxs-lookup"><span data-stu-id="67970-111">Child Elements</span></span>

|<span data-ttu-id="67970-112">要素</span><span class="sxs-lookup"><span data-stu-id="67970-112">Element</span></span>|<span data-ttu-id="67970-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="67970-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67970-114">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="67970-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="67970-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="67970-115">Optional element.</span></span><br /><br /> <span data-ttu-id="67970-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="67970-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="67970-117">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="67970-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="67970-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="67970-118">Optional element.</span></span><br /><br /> <span data-ttu-id="67970-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="67970-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="67970-120">EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="67970-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="67970-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="67970-121">Optional element.</span></span><br /><br /> <span data-ttu-id="67970-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="67970-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="67970-123">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="67970-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="67970-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="67970-124">Optional element.</span></span><br /><br /> <span data-ttu-id="67970-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="67970-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="67970-126">親要素</span><span class="sxs-lookup"><span data-stu-id="67970-126">Parent Elements</span></span>

|<span data-ttu-id="67970-127">要素</span><span class="sxs-lookup"><span data-stu-id="67970-127">Element</span></span>|<span data-ttu-id="67970-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="67970-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67970-129">TableRowEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="67970-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="67970-130">このテーブルエントリを使用する .NET 型、またはこのエントリを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="67970-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="67970-131">コメント</span><span class="sxs-lookup"><span data-stu-id="67970-131">Remarks</span></span>

<span data-ttu-id="67970-132">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="67970-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="67970-133">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="67970-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="67970-134">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="67970-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="67970-135">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="67970-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="67970-136">選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67970-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="67970-137">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67970-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="67970-138">参照</span><span class="sxs-lookup"><span data-stu-id="67970-138">See Also</span></span>

[<span data-ttu-id="67970-139">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="67970-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="67970-140">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="67970-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="67970-141">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="67970-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="67970-142">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="67970-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="67970-143">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="67970-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="67970-144">EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="67970-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="67970-145">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="67970-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="67970-146">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="67970-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
