---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)
description: TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)
ms.openlocfilehash: 22f304615c6433ffb67f3b4046b645d0c37be8a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645755"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="d5c07-103">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d5c07-103">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="d5c07-104">テーブルビューのこの定義に使用する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-104">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="d5c07-105">テーブル定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d5c07-105">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="d5c07-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の Entrycondition 要素を TableRowEntry (Format) の EntrySelectedBy 要素に指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d5c07-107">構文</span><span class="sxs-lookup"><span data-stu-id="d5c07-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d5c07-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-108">Attributes and Elements</span></span>

<span data-ttu-id="d5c07-109">次のセクションでは、属性、子要素、および SelectionCondition 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-109">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d5c07-110">属性</span><span class="sxs-lookup"><span data-stu-id="d5c07-110">Attributes</span></span>

<span data-ttu-id="d5c07-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d5c07-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d5c07-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-112">Child Elements</span></span>

|<span data-ttu-id="d5c07-113">要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-113">Element</span></span>|<span data-ttu-id="d5c07-114">説明</span><span class="sxs-lookup"><span data-stu-id="d5c07-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d5c07-115">TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d5c07-115">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="d5c07-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5c07-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d5c07-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d5c07-118">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="d5c07-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5c07-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d5c07-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="d5c07-121">EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="d5c07-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5c07-122">Optional element.</span></span><br /><br /> <span data-ttu-id="d5c07-123">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="d5c07-124">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-124">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="d5c07-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5c07-125">Optional element.</span></span><br /><br /> <span data-ttu-id="d5c07-126">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d5c07-127">親要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-127">Parent Elements</span></span>

|<span data-ttu-id="d5c07-128">要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-128">Element</span></span>|<span data-ttu-id="d5c07-129">説明</span><span class="sxs-lookup"><span data-stu-id="d5c07-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d5c07-130">TableRowEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d5c07-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="d5c07-131">このテーブルエントリを使用する .NET 型、またはこのエントリを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d5c07-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d5c07-132">解説</span><span class="sxs-lookup"><span data-stu-id="d5c07-132">Remarks</span></span>

<span data-ttu-id="d5c07-133">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5c07-133">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="d5c07-134">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d5c07-134">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="d5c07-135">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5c07-135">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="d5c07-136">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5c07-136">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="d5c07-137">選択条件の使用方法の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5c07-137">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d5c07-138">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5c07-138">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5c07-139">参照</span><span class="sxs-lookup"><span data-stu-id="d5c07-139">See Also</span></span>

[<span data-ttu-id="d5c07-140">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="d5c07-140">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d5c07-141">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="d5c07-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d5c07-142">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d5c07-142">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="d5c07-143">TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d5c07-143">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="d5c07-144">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-144">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d5c07-145">EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-145">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d5c07-146">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d5c07-146">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d5c07-147">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d5c07-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
